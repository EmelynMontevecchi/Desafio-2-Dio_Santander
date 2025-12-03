# RELATÓRIO DE IMPLEMENTAÇÃO DE SERVIÇOS AWS

**Data**: 03 de Dezembro de 2025  
**Empresa**: Abstergo Industries  
**Responsável**: Emelyn Montevechi

## Introdução

Este relatório apresenta o processo de implementação de ferramentas na empresa Abstergo Industries, realizado por João Silva. O objetivo do projeto foi elencar 3 serviços AWS com a finalidade de realizar diminuição de custos imediatos na infraestrutura em nuvem.

## Descrição do Projeto

O projeto de implementação de ferramentas foi dividido em 3 etapas, cada uma com seus objetivos específicos. A seguir, serão descritas as etapas do projeto:

**Etapa 1**  
- **Nome da ferramenta**: Amazon EC2 Savings Plans  
- **Foco da ferramenta**: Redução drástica no custo de instâncias EC2  
- **Descrição de caso de uso**: A empresa mantinha diversas instâncias EC2 no modelo On-Demand, com pagamento por hora cheia mesmo em horários de baixa utilização. Com a adoção do EC2 Savings Plans (compromisso de 1 ano), obtivemos descontos de até 66% em relação ao preço On-Demand, mantendo a mesma flexibilidade de família, região e sistema operacional.

**Etapa 2**  
- **Nome da ferramenta**: AWS Lambda + Amazon S3  
- **Foco da ferramenta**: Eliminação de servidores ociosos (serverless)  
- **Descrição de caso de uso**: Processos de ETL, redimensionamento de imagens e microsserviços internos eram executados em instâncias EC2 subutilizadas (média de 15% de CPU). Migrando essas workloads para AWS Lambda, eliminamos completamente os servidores parados e passamos a pagar apenas pelos milissegundos de execução e requests, gerando economia superior a 80% nesses serviços.

**Etapa 3**  
- **Nome da ferramenta**: Amazon S3 Intelligent-Tiering  
- **Foco da ferramenta**: Otimização automática de custos de armazenamento  
- **Descrição de caso de uso**: Mais de 80 TB de arquivos (logs, backups, documentos antigos) estavam na classe S3 Standard, mesmo sendo acessados raramente. Com a migração para S3 Intelligent-Tiering, o próprio AWS move automaticamente objetos não acessados por 30 dias para a camada Infrequent Access e, depois, para Archive Access, reduzindo os custos de armazenamento em até 68% sem qualquer intervenção manual.

## Conclusão

A implementação desses três serviços na Abstergo Industries resultará em uma redução imediata e significativa de custos na conta AWS (estimativa conservadora acima de 60% nos recursos migrados), maior escalabilidade e menor esforço operacional.  
Recomenda-se manter o monitoramento contínuo via AWS Cost Explorer e Budgets, além da expansão dessas práticas para outros serviços da empresa.

## Anexos

- **Planilha de projeção de economia com Savings Plans**  
  → https://docs.google.com/spreadsheets/d/1Q8kI5vR9v9exampleSavingsPlans/edit?usp=sharing  
  *(cópia pública da calculadora oficial da AWS já preenchida com exemplo da Abstergo Industries)*

- **Relatório comparativo do AWS Cost Explorer (antes × depois)**  
  → https://drive.google.com/file/d/1XampleCostExplorerBeforeAfter/view?usp=sharing  
  *(print em PDF com gráfico de redução de ~62% no custo mensal)*

- **Política de ciclo de vida do S3 Intelligent-Tiering aplicada**  
  → https://drive.google.com/file/d/1ExampleS3LifecyclePolicy/view?usp=sharing  
  *(print do console AWS mostrando a regra de transição automática para Infrequent Access e Archive)*

- **Dashboard de monitoramento de economia (AWS Cost Explorer + Budgets)**  
  → https://drive.google.com/file/d/1ExampleDashboardEconomia/view?usp=sharing

- **Documento de recomendações oficiais da AWS Well-Architected Framework – Pilar de Custo**  
  → https://docs.aws.amazon.com/pt_br/wellarchitected/latest/cost-optimization-pillar/welcome.html

- **Link do repositório completo com todos os prints e arquivos**  
  → https://github.com/seu-usuario/aws-custo-abstergo-industries

**Assinatura do Responsável pelo Projeto**:  
Emelyn Montevechi
