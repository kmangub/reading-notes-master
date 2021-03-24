# JSON Web Tokens

JSON web token (JWT) is a JSON object that is compact and secure to transmit information between parties. We can use JWTs to access APIs.

There are two ways we can use JWT and they are for authorization and information exchange. 

The JWT structure is broken down to three parts, separated by a comma and it's the **Header**, **Payload**, and the **Signature**. 

- Header has two parts, the type of token and the signing algorithm.
- Payload contains the claims, which are the statements about an entity and other data. There are three types of claims:
    - Registered Claims - recommended claims to provide interoperable claims.
    - Public Claims - Can be defined at will by those uisng JWT.
    - Private Claims - Custom claims created to share information between parties that agree on using them.

- Signature is used to verify the message wasn't changed along the way. We create it by taking the encoded header, the encoded payload, a secret, the algoritm in the header, and sign it.

JSON web tokens must be taken care of to prevent security issues. 

# Set Up

To set up, we will use the `djangorestframework_simplejwt` library:
    ```
    pip install djangorestframework_simplejwt
    ```
    
In our `settings.py` file:
    ```
    REST_FRAMEWORK = {
    'DEFAULT_AUTHENTICATION_CLASSES': [
        'rest_framework_simplejwt.authentication.JWTAuthentication',
        ],
    }
    ```

In our `urls.py`:
```
from django.urls import path
from rest_framework_simplejwt import views as jwt_views

urlpatterns = [
    # Your URLs...
    path('api/token/', jwt_views.TokenObtainPairView.as_view(), name='token_obtain_pair'),
    path('api/token/refresh/', jwt_views.TokenRefreshView.as_view(), name='token_refresh'),
]
```

## Example Code

`views.py`:

```
from rest_framework.views import APIView
from rest_framework.response import Response
from rest_framework.permissions import IsAuthenticated


class HelloView(APIView):
    permission_classes = (IsAuthenticated,)

    def get(self, request):
        content = {'message': 'Hello, World!'}
        return Response(content)
```

`urls.py`:
```
from django.urls import path
from myapi.core import views

urlpatterns = [
    path('hello/', views.HelloView.as_view(), name='hello'),
]
```

In the command line: 

```
http post http://127.0.0.1:8000/api/token/ username=vitor password=123
```

and the response should be a access and a refresh token.

To acces the protected views on the backend:

```
http http://127.0.0.1:8000/hello/ "Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ0b2tlbl90eXBlIjoiYWNjZXNzIiwiZXhwIjoxNTQ1MjI0MjAwLCJqdGkiOiJlMGQxZDY2MjE5ODc0ZTY3OWY0NjM0ZWU2NTQ2YTIwMCIsInVzZXJfaWQiOjF9.9eHat3CvRQYnb5EdcgYFzUyMobXzxlAVh_IAgqyvzCE"
```
> The access token will expire after 5 minutes. 

For a new refresh token, use the endpoint `/api/token/refresh/` in the command line:

```
http post http://127.0.0.1:8000/api/token/refresh/ refresh=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ0b2tlbl90eXBlIjoicmVmcmVzaCIsImV4cCI6MTU0NTMwODIyMiwianRpIjoiNzAyOGFlNjc0ZTdjNDZlMDlmMzUwYjg3MjU1NGUxODQiLCJ1c2VyX2lkIjoxfQ.Md8AO3dDrQBvWYWeZsd_A1J39z6b6HEwWIUZ7ilOiPE
```

We use refresh tokens to make sure the user still has the correct permissions. Refresh tokens only travel through POST data and the access token is sent through the HTTP header. 