# Integração ERP-Ecommerce com n8n

## Objetivo
Sincronizar produtos entre um ERP e uma plataforma de e-commerce, criando novos produtos ou atualizando existentes.

## Fluxo
1. **Obter produtos do ERP**: Requisição GET para a API do ERP
2. **Transformar dados**: Conversão para o formato esperado pelo e-commerce
3. **Verificar existência**: Consulta ao e-commerce usando codprod como SKU
4. **Decidir operação**: POST para novos produtos, PUT para existentes
5. **Executar operação**: Envio dos dados transformados
6. **Registrar log**: Armazenamento dos resultados em Google Sheets

## Estrutura de Dados
### ERP → E-commerce
- name → nomeecommerce
- price → price
- description → descricao
- categoryId → codprod
- imageUrl → imageUrl

## Logs
Registrados no Google Sheets com:
- SKU do produto
- Tipo de operação (POST/PUT)
- Status HTTP
- Erro (se houver)
- Timestamp da operação
