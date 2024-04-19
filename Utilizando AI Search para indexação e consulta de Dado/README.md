# Explore um índice de pesquisa Azure AI (UI)

Vamos imaginar que você trabalha para a Fourth Coffee, uma rede nacional de cafeterias. Pediram para você ajudar a construir uma solução de mineração de conhecimento que facilite a busca por insights sobre experiências do cliente. Você decide construir um índice de pesquisa Azure AI usando dados extraídos de avaliações de clientes.

Neste laboratório, você vai:

- Criar recursos Azure
- Extrair dados de uma fonte de dados
- Enriquecer dados com habilidades de IA
- Usar o indexador do Azure no portal Azure
- Consultar seu índice de pesquisa
- Revisar resultados salvos em uma Knowledge Store

## Recursos Azure necessários

A solução que você vai criar para a Fourth Coffee requer os seguintes recursos na sua assinatura Azure:

- Um recurso de pesquisa Azure AI, que vai gerenciar a indexação e consulta.
- Um recurso de serviços Azure AI, que fornece serviços de IA para habilidades que sua solução de pesquisa pode usar para enriquecer os dados na fonte de dados com insights gerados por IA.

> Nota: Seus recursos de pesquisa Azure AI e serviços Azure AI devem estar na mesma localização!

- Uma conta de armazenamento com contêineres de blob, que vai armazenar documentos brutos e outras coleções de tabelas, objetos ou arquivos.

## Criar um recurso de pesquisa Azure AI

Faça login no portal Azure.

Clique no botão + Criar um recurso, procure por pesquisa Azure AI e crie um recurso de pesquisa Azure AI com as seguintes configurações:

- Assinatura: Sua assinatura Azure.
- Grupo de recursos: Selecione ou crie um grupo de recursos com um nome único.
- Nome do serviço: Um nome único.
- Localização: Escolha qualquer região disponível.
- Nível de preço: Básico

Selecione Revisar + criar e, depois de ver a resposta Sucesso na validação, selecione Criar.

Depois que a implantação for concluída, selecione Ir para recurso. Na página de visão geral da pesquisa Azure AI, você pode adicionar índices, importar dados e pesquisar índices criados.

## Criar um recurso de serviços Azure AI

Você precisará provisionar um recurso de serviços Azure AI que esteja na mesma localização que seu recurso de pesquisa Azure AI. Sua solução de pesquisa usará este recurso para enriquecer os dados no armazenamento de dados com insights gerados por IA.

Volte para a página inicial do portal Azure. Clique no botão ＋Criar um recurso e procure por serviços Azure AI. Selecione criar um plano de serviços Azure AI. Você será levado a uma página para criar um recurso de serviços Azure AI. Configure-o com as seguintes configurações:

- Assinatura: Sua assinatura Azure.
- Grupo de recursos: O mesmo grupo de recursos que seu recurso de pesquisa Azure AI.
- Região: A mesma localização que seu recurso de pesquisa Azure AI.
- Nome: Um nome único.
- Nível de preço: Padrão S0
- Ao marcar esta caixa, reconheço que li e entendi todos os termos abaixo: Selecionado

Selecione Revisar + criar. Depois de ver a resposta Passou na validação, selecione Criar.

Aguarde a conclusão da implantação e, em seguida, veja os detalhes da implantação.

## Criar uma conta de armazenamento

Volte para a página inicial do portal Azure e, em seguida, selecione o botão + Criar um recurso.

Procure por conta de armazenamento e crie um recurso de conta de armazenamento com as seguintes configurações:

- Assinatura: Sua assinatura Azure.
- Grupo de recursos: O mesmo grupo de recursos que seus recursos de pesquisa Azure AI e serviços Azure AI.
- Nome da conta de armazenamento: Um nome único.
- Localização: Escolha qualquer localização disponível.
- Desempenho: Padrão
- Redundância: Armazenamento localmente redundante (LRS)

Clique em Revisar e, em seguida, clique em Criar. Aguarde a conclusão da implantação e, em seguida, vá para o recurso implantado.

Na conta de armazenamento Azure que você criou, no painel de menu à esquerda, selecione Configuração (em Configurações).

Altere a configuração para Permitir acesso anônimo ao blob para Habilitado e, em seguida, selecione Salvar.

## Fazer upload de documentos para o armazenamento Azure

No painel de menu à esquerda, selecione Contêineres.

Selecione + Contêiner. Um painel no lado direito se abre.

Insira as seguintes configurações e clique em Criar:

- Nome: coffee-reviews
- Nível de acesso público: Contêiner (acesso de leitura anônimo para contêineres e blobs)
- Avançado: sem alterações.