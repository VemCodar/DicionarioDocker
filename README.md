# Listagem de todos os comandos Docker.

É possível obter essa mesma listagem executando `docker --help`

Aqui está a tabela com uma coluna adicional contendo exemplos de uso para cada comando:

| Comando  | Descrição                                                                                           | Exemplo de Uso                                                                                       |
|----------|-----------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------|
| attach   | Anexa as entradas padrão locais, saídas e fluxos de erro a um contêiner em execução.              | `docker attach <container_id>`                                                                      |
| commit   | Cria uma nova imagem a partir das alterações de um contêiner.                                       | `docker commit <container_id> <new_image_name>`                                                      |
| cp       | Copia arquivos/pastas entre um contêiner e o sistema de arquivos local.                            | `docker cp <container_id>:<caminho_no_contêiner> <caminho_local>`                                    |
| create   | Cria um novo contêiner.                                                                            | `docker create <nome_da_imagem>`                                                                     |
| diff     | Inspecciona as alterações em arquivos ou diretórios no sistema de arquivos de um contêiner.        | `docker diff <container_id>`                                                                         |
| events   | Obtém eventos em tempo real do servidor.                                                            | `docker events`                                                                                      |
| export   | Exporta o sistema de arquivos de um contêiner como um arquivo tar.                                  | `docker export <container_id> > arquivo.tar`                                                         |
| history  | Mostra o histórico de uma imagem.                                                                  | `docker history <image_name>`                                                                        |
| import   | Importa o conteúdo de um arquivo tar para criar uma imagem de sistema de arquivos.                 | `docker import arquivo.tar`                                                                          |
| inspect  | Retorna informações de baixo nível sobre objetos Docker.                                             | `docker inspect <object_id>`                                                                         |
| kill     | Mata um ou mais contêineres em execução.                                                           | `docker kill <container_id>`                                                                         |
| load     | Carrega uma imagem de um arquivo tar ou STDIN.                                                      | `docker load < arquivo.tar`                                                                           |
| logs     | Busca os logs de um contêiner.                                                                      | `docker logs <container_id>`                                                                         |
| pause    | Pausa todos os processos dentro de um ou mais contêineres.                                          | `docker pause <container_id>`                                                                        |
| port     | Lista mapeamentos de porta ou um mapeamento específico para o contêiner.                             | `docker port <container_id>`                                                                         |
| rename   | Renomeia um contêiner.                                                                              | `docker rename <container_name> <new_container_name>`                                                |
| restart  | Reinicia um ou mais contêineres.                                                                   | `docker restart <container_id>`                                                                      |
| rm       | Remove um ou mais contêineres.                                                                     | `docker rm <container_id>`                                                                           |
| rmi      | Remove uma ou mais imagens.                                                                        | `docker rmi <image_id>`                                                                              |
| save     | Salva uma ou mais imagens em um arquivo tar (transmitido para STDOUT por padrão).                   | `docker save <image_name> > arquivo.tar`                                                             |
| start    | Inicia um ou mais contêineres parados.                                                             | `docker start <container_id>`                                                                        |
| stats    | Exibe um fluxo ao vivo das estatísticas de uso de recursos do(s) contêiner(es).                     | `docker stats <container_id>`                                                                        |
| stop     | Para um ou mais contêineres em execução.                                                           | `docker stop <container_id>`                                                                         |
| tag      | Cria uma tag TARGET_IMAGE que se refere a SOURCE_IMAGE.                                              | `docker tag <image_id> <new_image_name>:<tag>`                                                        |
| top      | Exibe os processos em execução de um contêiner.                                                     | `docker top <container_id>`                                                                          |
| unpause  | Despausa todos os processos dentro de um ou mais contêineres.                                        | `docker unpause <container_id>`                                                                      |
| update   | Atualiza a configuração de um ou mais contêineres.                                                  | `docker update --memory 512m <container_id>`                                                         |
| wait     | Bloqueia até que um ou mais contêineres parem, e então imprime seus códigos de saída.              | `docker wait <container_id>`                                                                         |

# Processo de criação de imagens

Aqui está uma lista de comandos Docker para realizar as ações solicitadas:

1. **Efetuar login no Docker Registry:**
   ```bash
   docker login <registry_url>
   ```
   - `<registry_url>` é o URL do Registry onde você deseja fazer login. Caso não informe essa url, o docker assume que é o Docker Registry

2. **Criar uma imagem a partir de um Dockerfile:**
   ```bash
   docker build -t <nome_da_imagem>:<tag> <caminho_para_o_Dockerfile>
   ```
   - `<nome_da_imagem>` é o nome que você deseja dar à imagem.
   - `<tag>` é a tag (versão ou identificador da versão) que você deseja atribuir à imagem. Por exemplo v1.0.0
   - `<caminho_para_o_Dockerfile>` é o caminho para o Dockerfile no sistema de arquivos local. Caso o comando seja executado na pasta onde encontra-se o arquivo DOCKERFILE, pode-se utilizar `.` ao invés do caminho.

3. **Publicar a imagem no Docker Registry:**
   ```bash
   docker push <nome_da_imagem>
   ```
   - `<nome_da_imagem>` é o nome da imagem que você deseja publicar.

4. **Rodar um contêiner com a imagem criada:**
   ```bash
   docker run -d --name <nome_do_contêiner> <nome_da_imagem>
   ```
   - `<nome_do_contêiner>` é o nome que você deseja dar ao contêiner.
   - `<nome_da_imagem>` é o nome da imagem que você deseja usar para criar o contêiner.

# Gerenciando Imagens

## Listando Imagens

Para listar as imagens Docker disponíveis localmente, você pode usar o comando `docker images` ou `docker image ls`. Ambos os comandos têm o mesmo efeito e fornecem uma lista das imagens Docker disponíveis no sistema local. Aqui está o comando:

```bash
docker images
```

ou

```bash
docker image ls
```

Ambos os comandos produzirão uma saída semelhante, mostrando informações sobre as imagens, como nome, tag, ID da imagem, tamanho e quando foram criadas.

## Removendo Imagens

Para apagar uma ou mais imagens Docker, você pode usar o comando `docker rmi`. Aqui estão os comandos para apagar imagens:

1. **Apagar uma imagem específica:**
   ```bash
   docker rmi <image_id>
   ```
   Substitua `<image_id>` pelo ID da imagem que você deseja apagar.

2. **Apagar várias imagens ao mesmo tempo:**
   ```bash
   docker rmi <image_id_1> <image_id_2> ... <image_id_n>
   ```
   Substitua `<image_id_1>`, `<image_id_2>`, etc., pelos IDs das imagens que você deseja apagar.

3. **Apagar todas as imagens não utilizadas (sem nenhum contêiner associado):**
   ```bash
   docker image prune
   ```
   Este comando apaga todas as imagens que não estão sendo usadas por nenhum contêiner.

Lembre-se de que você pode usar o nome da imagem em vez do ID da imagem se preferir. Certifique-se de substituir `<image_id>` pelos IDs reais das imagens que você deseja apagar. Se você usar o nome da imagem, ele deve ser o nome completo, incluindo a tag. Por exemplo: `<nome_da_imagem>:<tag>`.

# Gerenciando Contêineres

## Listando Contêineres

Para listar os contêineres em execução e os que estão parados, você pode usar os seguintes comandos Docker:

1. **Listar contêineres em execução:**
   
   ```bash
   docker ps
   ```

   Este comando lista todos os contêineres em execução no momento.

2. **Listar todos os contêineres, incluindo os parados:**
   
   ```bash
   docker ps -a
   ```

   Este comando lista todos os contêineres, tanto os em execução quanto os parados.

Se você deseja apenas listar os contêineres que estão parados (ou seja, não em execução), você pode usar um comando de filtro junto com o comando `docker ps -a`. Por exemplo:

```bash
docker ps -a --filter "status=exited"
```

Isso listará apenas os contêineres que estão no estado "exited" (parados).

## Removendo Contêineres

Para apagar um ou mais contêineres Docker, você pode usar o comando `docker rm`. Aqui estão os comandos:

1. **Apagar um contêiner específico:**
   ```bash
   docker rm <container_id>
   ```
   Substitua `<container_id>` pelo ID do contêiner que você deseja apagar.

2. **Apagar vários contêineres ao mesmo tempo:**
   ```bash
   docker rm <container_id_1> <container_id_2> ... <container_id_n>
   ```
   Substitua `<container_id_1>`, `<container_id_2>`, etc., pelos IDs dos contêineres que você deseja apagar.

3. **Apagar todos os contêineres parados:**
   ```bash
   docker container prune
   ```
   Este comando apaga todos os contêineres parados.

4. **Apagar um contêiner forçadamente (em execução ou parado):**
   ```bash
   docker rm -f <container_id>
   ```
   Este comando força a remoção do contêiner, mesmo que ele esteja em execução.

Lembre-se de que você pode usar o nome do contêiner em vez do ID do contêiner se preferir. Certifique-se de substituir `<container_id>` pelos IDs reais dos contêineres que você deseja apagar. Se você usar o nome do contêiner, ele deve ser o nome completo do contêiner. Por exemplo: `<nome_do_contêiner>`.
