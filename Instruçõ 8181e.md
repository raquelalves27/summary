# Instruções Symfony

[POO](Instruc%CC%A7o%CC%83%208181e/POO%20259eb.md)

[PHP UNIT](Instruc%CC%A7o%CC%83%208181e/PHP%20UNIT%208525a.md)

[Testes Automatizados ](Instruc%CC%A7o%CC%83%208181e/Testes%20Aut%20ae908.md)

[Modelagem de BD](Instruc%CC%A7o%CC%83%208181e/Modelagem%20%208464a.md)

Oi gente 🙂

Aqui é a Raquel e resolvi registrar todos comandos que fiz seguindo a documentação Symfony aqui pra vocês. Sei que pode e é difícil entender a documentação em primeira analise, então espero que esse arquivo ajude.

Em primeira mão você pode achar que esta incompleto, uma explicação pra isso é: SIM EU AINDA ESTOU ESTUDANDO SOBRE ESSE ASSUNTO, MAS IREI COMPLEMENTAR ASSIM QUE POSSÍVEL,  E SE VOCÊ TB QUISER AJUDAR COM ESSA DOCUMENTAÇÃO, É SO ME MANDAR UM “ALÔ” QUE VOCÊ PODE VIRAR UM EDITORA(O). 😉

# Logo esse arquivo será movido para o GitHub, e minhas anotações vão estar disponíveis para qualquer pessoa, mas não se preocupe, estou aqui para qualquer suporte.

# Instale o php

Será necessário que você baixe o php 8.0.2 segundo a documentação.

**obs: V***ersão SYMFONY 6.0*

# Instale o *Composer*

A seguir anexo o link para Download. 

Link: [https://getcomposer.org/download](https://getcomposer.org/download/)/

- Se você decidir não seguir a documentação de download, colocarei a seguir como você pode fazer.

 No terminal execute:

```
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"

php -r "if (hash_file('sha384', 'composer-setup.php') === '906a84df04cea2aa72f40b5f787e49f22d4c2f19492ac310e8cba5b96ac8b64115ac402c8cd292b8a03482574915d1a8') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"

 php composer-setup.php

 php -r "unlink('composer-setup.php');"
```

---

- Você pode instalar o composer dentro de um arquivo.Especificando o nome do arquivo.
         Exemplo, execute no terminal:

no lugar de composer troque pelo nome do seu arquivo

```
php composer-setup.php --filename=composer
```

---

**Importante.**

Sempre que você der um git clone(baixando pela primeira vez a pasta de arquivos, você deverá instalar o composer.)

- Partindo do pensamento em que você acabou de baixar o código de outro desenvolvedor a partir do gitLab/gitHub:

Execute no Terminal:

```
$ composer install
```

# Instalando o Symfony

- Usando o Ubuntu execute no terminal:

```
echo 'deb [trusted=yes] https://repo.symfony.com/apt/ /' | sudo tee /etc/apt/sources.list.d/symfony-cli.list

```

```
sudo apt update

```

```
sudo apt install symfony-cli
```

# Criando a aplicação Symfony

Execute no terminal:

```
symfony new my_project

(No lugar de my_project, você pode escrever o nome que foi definido para o seu projeto.)

```

---

O `symfony` também fornece uma ferramenta para verificar se o seu computador atende a todos
 requisitos.  Abra o terminal do console e execute este comando:

```
symfony check:requirements
```

Quando estamos trabalhando em um aplicativo Symfony existente pela primeira vez, pode ser útil para executar este comando que exibe informações sobre o projeto:

---

**A PARTIR DE AGORA EU VOU ENTRAR NO VSCODE E EXECUTAR OS COMANDOS DENTRO  DO MEU DIRETÓRIO CRIADO.**

-dentro do arquivo que vc criou.

```
php bin/console about
```

# Executando sua aplicação

LEMBRE: **EXECUTAR OS COMANDOS DENTRO  DO MEU DIRETÓRIO CRIADO.**

Bem, se você está seguindo os passos que eu descrevi aqui ate agora, suponho que tenha acabado de criar sua aplicação. 🙂Parabéns.

Por enquanto é um projeto vazio mais você pode fazer uma simples verificação se esta tudo bem.

- O próprio symfony fornece um servidor local para testarmos a nossa aplicação.

No terminal do VSCODE execute:

```
symfony serve
```

Abra seu navegador e navegue até `http://localhost:8000/`.  Se tudo esta funcionando, você verá uma página de boas-vindas.

---

# Opcional:

## Instalando Pacotes

Antes de continuar, pra melhor didática eu vou esclarecer alguns termos que podemos encontrar pela frente.

> Bundles → O Symfone chama os pacotes que fornecem recursos que podemos instalar de bundles.
> 

> Symfone Flex → Plugin de automatização de algumas configurações. (Uma ferramenta para simplificar a instalação/remoção de pacotes em 
 Aplicativos Symfony.)
> 
- Tecnicamente falando, o Symfony Flex é um plugin do Composer  que é instalado por padrão ao criar um novo aplicativo Symfony e que automatiza as tarefas mais comuns das aplicações Symfony .
- Usar o Symfony FLex é OPCIONAL.

Para testar se o seu Symfony ja esta com o Flex incluido é so run estes comandos:

```
composer require logger
```

Se você executar esse comando em um aplicativo Symfony que não usa Flex, você vera um erro do Composer explicando que `logger`não é um nome de pacote válido.
 No entanto, se o aplicativo tiver o Symfony Flex instalado, esse comando instala e habilita todos os pacotes necessários para usar o logger oficial do Symfony.

---

## Recursos de depuração

Por exemplo, para adicionar recursos de depuração em seu aplicativo, você pode executar:

```
composer require --dev debug
```

## Vulnerabilidade de segurança

O Symfony fornece um comando para verificar se as dependências do seu projeto contêm vulnerabilidade:

```
symfony check:security
```

Uma boa prática de segurança é executar este comando regularmente para poder atualizar ou substituir as dependências comprometidas o mais rápido possível.

---

---

---

# Criando minha page Symfony

É necessário que duas etapas sejam feitas.

1. Criar uma **Rout.**

Uma rota é a URL que aponta para o controlador.

 Rota define o URL para sua
 página ( `path`) e o que o  `controller`chama.

 2. Criar um **Controller**.

Em poucas palavras o controller é o que se deve fazer quando recebemos uma request.

É uma função PHP, Você pega as informações da solicitação recebida e as usa para criar um Symfony `Response`objeto, que pode conter um JSON.

*Crie um controlador e um método* : Esta é uma função onde *você* constrói a página e, finalmente, 
 devolver um `Response`objeto.

---

## [Confira a estrutura do projeto](https://symfony.com/doc/current/page_creation.html#checking-out-the-project-structure)

`config/`
Contém... configuração!. Você configurará rotas, 
 [serviços](https://symfony.com/doc/current/service_container.html) e pacotes. 

  `src/`     

Todo o seu código PHP mora aqui.
                    

 `templates/`
Todos os seus templates Twig ficam aqui.

Na maioria das vezes, você estará trabalhando em `src/`,  `templates/`ou `config/`.

`bin/`
O famoso `bin/console`arquivo vive aqui (e outros, menos importantes arquivos executáveis).

`var/`
 É aqui que os arquivos criados automaticamente são armazenados, como arquivos de cache( `var/cache/`) e registros ( `var/log/`).

 `vendor/`
Bibliotecas de terceiros (ou seja, "fornecedor") moram aqui! Estes são baixados através do [Composer](https://getcomposer.org/) gerenciador de pacotes. 
                     

`public/`
Esta é a raiz do documento do seu projeto: você coloca todos os arquivos acessíveis publicamente aqui.

E quando você instala novos pacotes, novos diretórios serão criados automaticamente
 quando necessário.

# Roteamento

Podemos definir rotas no caminho 

|_ `config/routes.yaml`

 our

|_ Em forma de anotação

```
Ex.
/**
+    * @Route("/index/show_clients")
+    */
```

## Criando rotas

Rota é basicamente como sua url vai se comportar. 

Para garantir que Você pode definir suas rotas em forma de anotação, execute no terminal:

```
composer require doctrine/annotations

//Esta configuração diz ao Symfony para procurar rotas definidas como anotações no qualquer classe PHP armazenada no src/Controller/diretório.
```

```
COMO FICA NO VSCODE

class BlogController extends AbstractController
{
    /**
     * @Route("/blog", name="blog_list")
     */
    public function list()
    {
        // ...
    }
}
```

Cuidado

Se você definir várias classes PHP no mesmo arquivo, o Symfony carrega apenas as
 rotas da primeira classe, ignorando todas as outras rotas.

## O que é o bin/console

O bin/console oferece uma lista de comandos para depuração.

- ajudar a gerar código
- gera migrações de banco de dados
- listar rotas
- usar o migrations

e etc.

Para listar todos os comandos possíveis é só executar no terminal :

```
php bin/console
```

Para listar todas as rotas que existem na aplicação:

```
php bin/console debug:router
```

## **[Métodos HTTP correspondentes](https://symfony.com/doc/current/routing.html#matching-http-methods)**

Por padrão, as rotas correspondem a qualquer verbo HTTP ( `GET`,  `POST`,  `PUT`, etc)
 Use o `methods`opção para restringir os verbos aos quais cada rota deve responder.

```
/**
     * @Route("/api/posts/{id}", methods={"GET"})
     */
```

# `request`

`request`: Equivalente a `$_POST`;

Um objeto Request contém informações sobre a solicitação do cliente.

Cada propriedade é um ParameterBag instância (ou uma subclasse de), que é uma classe de titular de dados: Todas as de ParameterBag instâncias métodos para recuperar e atualizar seus dados:

`All()` Retorna os parâmetros;

`Keys()`Retorna as chaves de um parâmetro;

`Replace()` Substitui os parâmetros atuais para um novo;

`Add()`  adiciona parâmetros;

`get()` Retorna o parâmetro;

`set()` Defini um parâmetro;

`has()` Retorna TRUE se um parâmetro tiver sido definido definido.

`remove()` remove os parâmetros setados 

---