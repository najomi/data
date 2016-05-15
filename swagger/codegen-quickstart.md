## Основы работы с swagger-codegen

Сперва скачиваем релиз:

```sh
# wget http://repo1.maven.org/maven2/io/swagger/swagger-codegen-cli/2.1.6/swagger-codegen-cli-2.1.6.jar \
    -O /opt/swagger-codegen-cli.jar
```

Делаем для него обёртку:

```sh
# cat <<- EOF > /usr/local/bin/swagger-codegen
	#!/bin/bash
	java -jar /opt/swagger-codegen-cli.jar $@
	EOF
# chmod +x /usr/local/bin/swagger-codegen
```

Без аргументов - он выведет список доступных платформ

```sh
$ swagger-codegen
Available languages: [android, aspnet5, async-scala, csharp, dart, flash,
                      python-flask, go, java, jaxrs, jaxrs-cxf, jaxrs-resteasy,
                      inflector, javascript, javascript-closure-angular, jmeter,
                      nodejs-server, objc, perl, php, python, qt5cpp, ruby, scala,
                      scalatra, silex-PHP, sinatra, slim, spring-mvc, dynamic-html,
                      html, swagger, swagger-yaml, swift, tizen, typescript-angular,
                      typescript-node, akka-scala, CsharpDotNet2, clojure,
                      haskell-servant]
```

Документация доступна по команде help
```sh
$ swagger-codegen help
usage: swagger-codegen-cli <command> [<args>]

The most commonly used swagger-codegen-cli commands are:
    config-help   Config help for chosen lang
    generate      Generate code with chosen lang
    help          Display help information
    langs         Shows available langs
    meta          MetaGenerator. Generator for creating a new template set and configuration for Codegen.  The output will be based on the language you specify, and includes default templates to include.

See 'swagger-codegen-cli help <command>' for more information on a specific
command.
```

Создадим php клиент и сервер по документации:
```sh
$ swagger-codegen generate -i swagger.yaml -l php -o ./php-client/
$ swagger-codegen generate -i swagger.yaml -l silex-PHP -o ./php-server/
```




