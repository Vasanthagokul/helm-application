helm-auth-backend is a dependency for helm-users-backend

I am using the free shared cluster of mongodb

if mongodb is already existing for you, update the connection string to use your personal mongodb cluster (env variable in helm-users-backend).

helm install login-backend -n testing

kubectl port-forward service/users-service 3000:3000

## In postman
(if you are portforwarding to localhost)
http://localhost:3000/signup
message body: raw
{
  "email":"test@test123.com",
  "password":"test123"
}

example return message: "user successfully registered"

http://localhost:3000/login
message body: raw
{
  "email":"test@test123.com",
  "password":"test123"
}

return message will be returned with login token
