Automação RPA para Relatório de Vendas 

Este projeto é uma automação desenvolvida com UiPath, cujo objetivo é gerar relatórios de vendas a partir de um arquivo PDF de vendas, aplicando regras de negócio e conversão de câmbio para BRL, e finalmente, validando os vendedores e gerando o relatório final em formato PDF.

Estrutura do Repositório
📁 Pasta resources

A pasta resources contém todos os arquivos essenciais para o processo de automação. Eles são utilizados nas diferentes etapas do robô.

Sales List.pdf: Arquivo contendo os dados de vendas em formato PDF.

Sales Report Template.xlsx: Template do relatório final em Excel.

Vendor List.xlsx: Lista de vendedores contendo os dados necessários para a validação.

📄 Arquivos de Log e Configuração

O projeto usa dois arquivos principais para armazenar logs e configurações:

log.txt: Armazena os logs gerados pela automação, incluindo erros e status de execução.

Formato de exemplo do arquivo log.txt:

2025-09-17 08:15:05 - Início do processo de conversão de PDF para Excel.
2025-09-17 08:16:20 - API de câmbio chamada com sucesso.
2025-09-17 08:18:30 - Finalizado processo de criação de relatório.


config.txt: Arquivo de configuração onde você define caminhos, credenciais de e-mail, e configurações da API de câmbio.

Formato de exemplo do arquivo config.txt:

[Paths Relativos raiz do projeto]
* sales_list_pdf_path = resources\Sales List.pdf
* sales_report_template_path = resources\Sales Report Template.xlsx
* vendor_list_excel_path = resources\Vendor List.xlsx
* output_path = resources\outputs
* logPath = resources\log.txt
* sales_report_output_path = resources\resultados

[Email]
* email_from = seuemail@dominio.com
* email_to = destinatario@dominio.com
* email_password = sua_senha
* smtp_server = smtp-mail.dominio.com
* smtp_port = 587

[API]
* exchange_rate_api = http://economia.awesomeapi.com.br/json/last/USD-BRL

🛠️ Configuração do Projeto

Arquivo config.txt:
O arquivo config.txt é fundamental para configurar o projeto. Ele define os caminhos dos arquivos de entrada (como o PDF de vendas e o template de relatório), as credenciais de e-mail para envio de relatórios, e o endpoint da API de câmbio para conversão das moedas para BRL.

Seção Paths Relativos raiz do projeto:

Define os caminhos relativos para os arquivos necessários.

Exemplo: sales_list_pdf_path = resources\Sales List.pdf.

Seção Email:

Define as credenciais de e-mail para envio de relatórios.

Exemplo: email_from = seuemail@dominio.com.

Seção API:

Configura a URL da API de câmbio para obter as taxas de conversão.

Exemplo: exchange_rate_api = http://economia.awesomeapi.com.br/json/last/USD-BRL.

Logs:
Durante a execução, os logs são gerados e armazenados em log.txt. Eles servem para monitorar o progresso do processo, capturar eventuais erros e garantir que cada etapa foi concluída com sucesso.

📝 Conclusão

Este projeto foi desenvolvido para automatizar o processo de geração de relatórios de vendas. Para garantir flexibilidade, o robô utiliza configurações externas que podem ser ajustadas facilmente pelo arquivo config.txt.

A automação está parcialmente completa, e os pontos futuros incluem a integração com a API dos Correios para obter endereços, além de melhorias na resolução de CAPTCHA usando um serviço pago, como o 2Captcha.
