# keycloak配置oidc connect
keycloak配置oidc connect，即外部套一层已加密登录的keycloak来进行登录
## 1、配置Identity providers(源keycloak操作)
![Alt text](./keycloak/identity-1.png)
![Alt text](./keycloak/identity-2.png)
![Alt text](./keycloak/identity-3.png)
其中client ID和Client Secret来自已配置好的keyclaok
## 2、在示例的https://kunlun.shijicloud.com/auth/realm/kunlun-sso的keycloak进行配置(目标keycloak操作)
![Alt text](./keycloak/client.png)
创建对应的groups
![Alt text](./keycloak/groups.png)
![Alt text](./keycloak/groups-scopes.png)
创建role
![alt text](image.png)
配置groups
![alt text](image-1.png)

## 3、配置mapper(在源keycloak操作)
创建groups
![Alt text](./keycloak/groups-client.png)
配置groups的admin权限
![alt text](image-3.png)
![Alt text](./keycloak/mapper.png)
此时使groups进行权限的映射
## 4、配置登录默认跳转
![Alt text](./keycloak/identity-provider-redirect.jpg)
![Alt text](./keycloak/redirect-config.png)
default identity provider参数必须与idenity provider的Alias值一致