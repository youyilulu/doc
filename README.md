## 技术调研

### 前端

- https://github.com/FEMessage/el-form-renderer
- https://github.com/FEMessage/el-data-table

### 后端

- http://blog.didispace.com/spring-security-oauth2-xjf-1/
  
### OAuth2

#### 两种方案

| 方案                         | 优点            | 缺点                  | 优化方案                                                   |
| ---------------------------- | --------------- | --------------------- | ---------------------------------------------------------- |
| 目前云筑智联采用的jwt token  | 不需要存储token | 已授权的token难以撤销 | 利用redis记录token，每次认证都需要检查redis中token是否存在 |
| 持久化存储token，如JdbcToken | token可控度高   | 实现较jwt麻烦<br/>spring-security-oauth2的token生成算法是黑盒，取不到token包含的信息，例如过期时间等，对资源服务器非常不友好（因为要引入security包），需要改造         | 不停地码砖                                                 |

#### 参考文章

- [利用Redis撤销JSON Web Token产生的令牌](https://blog.csdn.net/chszs/article/details/47081065)

#### token enhancer
- 可定制token，了解一下[OAuth2AccessToken](https://docs.spring.io/spring-security/oauth/apidocs/org/springframework/security/oauth2/common/OAuth2AccessToken.html)

## 问题

- [ ] 创建项目是否还需要从集采创建？
- [ ] 项目上创建用户还需不需要选组织？
