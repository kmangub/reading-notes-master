# Permissions
Permissions are used to grant or deny access for different classes of users to different parts of the API.

Before any code is allowed to proceed, permission checks need to be established in the `request.user` and `request.auth`. 

Permissions are determined if any permission checks fail an `exceptions.PermissionDenied` or `exceptions.NotAuthenticated`.

A 403 response means forbidden and 401 means unauthorized.

- `AllowAny` allows unrestricted access regardless if the request is authenticated or not.

- `IsAuthenticated` class in REST framework allows access to users.

- `IsAuthenticatedOrReadOnly` class is less restrictive and has read only access.

- `IsAdminUser`permission class will deny permission to any user. 

Custom permissions will override `BasePermission` and use either, or both two methods:

- `.has_permission(self, request, view)`
- `.has_object_permission(self, request, view, obj)`

The methods above should return True to grant access.

Below are some examples:

```
from rest_framework import permissions

class BlocklistPermission(permissions.BasePermission):
    """
    Global permission check for blocked IPs.
    """

    def has_permission(self, request, view):
        ip_addr = request.META['REMOTE_ADDR']
        blocked = Blocklist.objects.filter(ip_addr=ip_addr).exists()
        return not blocked
```

The code above is permission class that checks the incoming request's IP address against a blocklist, and denies the request if the IP has been blocked.

```
class IsOwnerOrReadOnly(permissions.BasePermission):
    """
    Object-level permission to only allow owners of an object to edit it.
    Assumes the model instance has an `owner` attribute.
    """

    def has_object_permission(self, request, view, obj):
        # Read permissions are allowed to any request,
        # so we'll always allow GET, HEAD or OPTIONS requests.
        if request.method in permissions.SAFE_METHODS:
            return True

        # Instance must have an attribute named `owner`.
        return obj.owner == request.user
```

The code above is an object-level permission.