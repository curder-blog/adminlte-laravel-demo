## 安装

### 环境文件

在项目的根目录中附带一个`.env.example`文件，请将其拷贝重命名为`.env`。可以使用如下命令完成操作`cp .env.example .env`。

> 注意：确保您的系统上显示隐藏的文件。


### Composer

laravel项目依赖通过`[composer](http://getcomposer.org/)`工具进行管理。

第一步是通过在终端中进入到项目中并输入以下命令来安装依赖

```php
composer install
```


### 创建数据库

在服务器上创建数据库，然后更新项目根目录下的`.env`文件上如下的相关行：

```
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=homestead
DB_USERNAME=homestead
DB_PASSWORD=secret
```

更新上面的行已完成数据库相关设置。

### artisan命令

我们要做的第一件事就是设置 Laravel 在进行加密时使用的密钥。


```php
php artisan key:generate
```

应该看到一条绿色消息，指出您的密钥已成功生成，以及你应该看到`.env`文件中的`app_key`变量反映出来。

现在是时候查看数据库连接信息是否正确。运行内置的迁移来创建数据库表

```php
php artisan migrate
```

如果没有看到错误，应该会看到每个迁移表的消息，而不是数据库连接信息很可能不正确。

运行数据库迁移文件以添加一些默认数据

```php
php artisan db:seed
```

应该得到每个迁移文件的消息，并且应该可以看到数据库表中的信息。

### 启动本地服务器
```
php artisan serv
```
地址: `http://127.0.0.1:8000` 邮箱: `admin@example.com` 密码：`123456`

邮箱和密码在迁移文件`database\seeds\AdminUserSeeder.php`中定义。

