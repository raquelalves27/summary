> :warning: Rascunho ainda em produção.

“_Na minha maquina funciona!_” e uma frase ouvida/proferida por quem programa com frequência, na maioria dos casos isso acontece pois na sua maquina ha dependências e versões diferentes da outra maquina.

Não seria massa se existisse uma forma de “fazer uma copia” do seu PC onde o programa esta funcionando direitinho e mandar pro seu amigo(a)? **E isso que Docker faz**.

---

O **Docker** isola a sua aplicação em um contêiner virtual como se fosse o sistema operacional (**host**) onde sua aplicação esta rodando.

![Untitled](https://user-images.githubusercontent.com/78993701/159544859-58849dee-60ba-412f-a583-9598eae11f19.png)

- Essa “copia” para o contêiner se chama **image**.
- **image** é um modelo onde você define o sistema operacional, bibliotecas, dependências e regras. Disponibilizando-a para uso nos contêiners.

## Vantagens do Docker em relação a uma Virtual Machine

- Nao necessita fazer boot do sistema operacional.
- o contêiner docker pega emprestado os recursos do sistema operacional host.
- Leve de rodar.

:warning: Para ter o reaproveitamento de kernel e necessário que o sistema operacional hospedeiro seja linux.
