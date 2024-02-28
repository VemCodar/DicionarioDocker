Listagem de todos os comandos Docker.

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
