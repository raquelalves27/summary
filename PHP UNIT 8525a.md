# PHP UNIT

Em primeira mão você pode achar que esta incompleto, uma explicação pra isso é: SIM EU AINDA ESTOU ESTUDANDO SOBRE ESSE ASSUNTO, MAS IREI COMPLEMENTAR ASSIM QUE POSSÍVEL,  E SE VOCÊ TB QUISER AJUDAR COM ESSA DOCUMENTAÇÃO, É SO ME MANDAR UM “ALÔ” QUE VOCÊ PODE VIRAR UM EDITORA(O). 😉

PHPUNIT  requer a extensão do [dom](http://php.net/manual/en/dom.setup.php) , do [json](http://php.net/manual/en/json.installation.php), do [pcre](http://php.net/manual/en/pcre.installation.php), [reflection](http://php.net/manual/en/reflection.installation.php), e [sp](http://php.net/manual/en/spl.installation.php) que são habilitadas por padrão no php. Essas extensões como já vem habilitadas não podem ser desativadas.

[https://www.youtube.com/watch?v=1oTRpTPEyX0&list=PL3j2sfzg3FPsPiaDUmDDKNvco49YMdj8f&index=6](https://www.youtube.com/watch?v=1oTRpTPEyX0&list=PL3j2sfzg3FPsPiaDUmDDKNvco49YMdj8f&index=6)

Para que o PHPUNIT seja mais informativo é necessário a seguinte configuração no arquivo PHP.ini (arquivo usado para teste):

```
memory_limit=-1
error_reporting=-1
log_errors_max_len=0
zend.assertions=1
assert.exception=1
xdebug.show_exception_trace=0
```

O caminho mais facil para instalar o PHPUNIT é fazendo o download do [PHP Archive](http://php.net/phar). Que tem todas as dependências que o PHPUNIT precisa.

Se a extensão [Suhosin](http://suhosin.org/) estiver ativada , você precisa permitir a execução para o PHAR no seu PHP.INI

```
suhosin.executor.include.whitelist = phar
```

## Instalando o phpUnit

no terminal com o composer instalado é so executar : 

```
composer require --dev phpunit/phpunit
```