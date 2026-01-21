Gera dicionário de logs e o atualiza durante o código, serializando para ser exibido conforme a etapa/módulo da execução. 
Utiliza um arquivo de configuração padrão carregado em um dicionário de strings e objetos, como o config do orchestrator. Lá estão parâmetros customizáveis para a execução da automação, com a finalidade de evitar hardcoded.
Utiliza conexão com o Outlook 365 e atividades do pacote 365 da UiPath para enviar o email. Este pacote foi utilizado por ser um dos mais utilizados em ambientes corporativos.
Realiza o processamento de emails em uma caixa do Outlook 365 para filtrar apenas com determinado assunto (realiza 3 tipos de filtro para diminuir a chance de não entrar no filtro por case sensitive) e processa
os anexos dentro do email filtrado, salvando-os em uma pasta definida nas configurações. Utiliza um arquivo estruturado em JSON para salvar o histórico de emails já processados pelo MessageID e seus anexos com o nome do anexo e o índice do mesmo dentro do email.
Em caso do anexo estar corrompido ou o email filtrado não possuir anexos, move o email para outra pasta na caixa de entrada.

O módulo D lê os PDFs dentro da pasta definida pelo usuário e extrai informações de CEP e CPF, validando estes dois campos e armazenando em uma linha de dados por arquivo. Ao final da execução, gera um CSV com essas
informações dos PDFs processados.
