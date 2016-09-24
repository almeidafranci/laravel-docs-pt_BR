# Instalação

- [Instalação](#installation)
    - [Requisitos do Servidor](#server-requirements)
    - [Instalando Laravel](#installing-laravel)
    - [Configuração](#configuration)

<a name="installation"></a>
## Instalação

<a name="server-requirements"></a>
### Requisitos do Servidor

O framework Laravel possui alguns requisitos de sistema. É claro que todos esses requisitos são satisfeitos pela máquina virtual [Laravel Homestead](/docs/{{version}}/homestead), portanto é altamente recomendado que você utilize Homestead como o seu ambiente de desenvolvimento local.

Contudo, se você não estiver utilizando Homestead, você deverá ter certeza que seu servidor corresponde aos seguintes requisitos:

<div class="content-list" markdown="1">
- PHP >= 5.6.4
- Extensão PHP OpenSSL
- Extensão PHP PDO
- Extensão PHP Mbstring
- Extensão PHP Tokenizer
</div>

<a name="installing-laravel"></a>
### Instalando Laravel

Laravel utiliza o [Composer](http://getcomposer.org) ara gerenciar suas dependências. Portanto, antes de usar o Laravel, certifique-se de ter o Composer instalado na sua máquina.

#### Através do Instalador do Laravel

Inicialmente, baixe o instalador do Laravel utilizando o Composer:

    composer global require "laravel/installer"

Certifique-se de adicionar o diretório `~/.composer/vendor/bin` (ou o diretório equivalente para o seu sistema operacional) à sua variável $PATH de forma que o executável `laravel` possa ser localizado pelo seu sistema.

Uma vez instalado, o comando `laravel new` irá criar uma nova instalação do Laravel no diretório que você especificar. Por exemplo, `laravel new blog` irá criar um diretório chamado `blog` contendo uma nova instalação do Laravel com todas as suas dependências já instaladas:

    laravel new blog

#### Através do Composer Create-Project

Como alternativa, você também pode instalar o Laravel através do Composer, utilizando o comando `create-project` no seu terminal:

    composer create-project --prefer-dist laravel/laravel blog

#### Servidor de Desenvolvimento Local

Se você possui PHP instalado localmente e gostaria de utilizar o servidor de desenvolvimento incluído no PHP como servidor para sua aplicação, você pode utilizar o comando `serve` do Artisan. Esse comando irá iniciar um servidor de desenvolvimento em `http://localhost:8000`:

    php artisan serve

Certamente, opções mais robustas de desenvolvimento local estão disponíveis através de [Homestead](/docs/{{version}}/homestead) e [Valet](/docs/{{version}}/valet).

<a name="configuration"></a>
### Configuração

#### Diretório Público

After installing Laravel, you should configure your web server's document / web root to be the `public` directory. The `index.php` in this directory serves as the front controller for all HTTP requests entering your application.

#### Arquivos de Configuração

All of the configuration files for the Laravel framework are stored in the `config` directory. Each option is documented, so feel free to look through the files and get familiar with the options available to you.

#### Permissões de Diretório

After installing Laravel, you may need to configure some permissions. Directories within the `storage` and the `bootstrap/cache` directories should be writable by your web server or Laravel will not run. If you are using the [Homestead](/docs/{{version}}/homestead) virtual machine, these permissions should already be set.

#### Chave da Aplicação

The next thing you should do after installing Laravel is set your application key to a random string. If you installed Laravel via Composer or the Laravel installer, this key has already been set for you by the `php artisan key:generate` command.

Typically, this string should be 32 characters long. The key can be set in the `.env` environment file. If you have not renamed the `.env.example` file to `.env`, you should do that now. **If the application key is not set, your user sessions and other encrypted data will not be secure!**

#### Configuração Adicional

Laravel needs almost no other configuration out of the box. You are free to get started developing! However, you may wish to review the `config/app.php` file and its documentation. It contains several options such as `timezone` and `locale` that you may wish to change according to your application.

You may also want to configure a few additional components of Laravel, such as:

<div class="content-list" markdown="1">
- [Cache](/docs/{{version}}/cache#configuration)
- [Database](/docs/{{version}}/database#configuration)
- [Session](/docs/{{version}}/session#configuration)
</div>

Once Laravel is installed, you should also [configure your local environment](/docs/{{version}}/configuration#environment-configuration).
