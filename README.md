# Nexus Urbano: SaaS para Gestão e Validação de Títulos de Propriedade

![Status](https://img.shields.io/badge/Status-Concluído%20(PFC1)-success)
![Architecture](https://img.shields.io/badge/Architecture-Serverless%20%7C%20BaaS-blue)
![Security](https://img.shields.io/badge/Security-AES--256%20%7C%20RLS-red)

> **Aviso de Propriedade e Confidencialidade (LGPD):** > Este repositório atua exclusivamente como um **Showcase Arquitetural** para fins de avaliação acadêmica (Trabalho de Conclusão de Curso - Engenharia da Computação). Como o sistema foi desenvolvido para a administração pública municipal, o código-fonte integral, as chaves criptográficas e as credenciais de acesso ao banco de dados estão omitidos por questões de conformidade com a Lei Geral de Proteção de Dados (LGPD) e protocolos de segurança da informação governamental.

## 📌 Sobre o Projeto
O **Nexus Urbano** é um *Software as a Service* (SaaS) multilocatário concebido para modernizar a Regularização Fundiária Urbana (REURB). Ele substitui fluxos analógicos vulneráveis a fraudes por um ecossistema digital blindado.

A plataforma permite que entes municipais cadastrem cidadãos, anexem provas documentais e emitam títulos de propriedade com rastreabilidade forense, gerando documentos em PDF com *QR Codes* dinâmicos validados em tempo real via portal público de transparência.

## 🏗️ Arquitetura e Tecnologias
O sistema foi projetado sob o paradigma *Serverless*, priorizando a alta disponibilidade, escalabilidade horizontal e o princípio do privilégio mínimo:

- **Frontend & Rendering:** Vanilla JS, HTML5, CSS3. Renderização descentralizada (Client-side) de PDFs visando economia de processamento (Teoria das Filas) utilizando `html2canvas` e `jsPDF`.
- **Backend as a Service (BaaS):** Supabase.
- **Banco de Dados:** PostgreSQL com aplicação estrita de *Row Level Security* (RLS) para isolamento lógico de jurisdições (*Tenants*).
- **Segurança e Borda:** Cloudflare Web Application Firewall (WAF) mitigando ataques DDoS e operando na camada 7 do Modelo OSI.
- **Criptografia e Auditoria:** Algoritmo AES-256 para ofuscação de dados civis (PII) e Hash SHA-256 para imutabilidade da "Caixa Preta" de auditoria forense.

## 📂 Artefatos Disponibilizados
Neste repositório, você encontrará a documentação técnica que embasa as decisões de engenharia:
- `\diagramas`: Modelagem UML completa (Diagrama de Implantação, Entidade-Relacionamento, Casos de Uso, Sequência e Máquina de Estados).
- `\exemplos_arquiteturais`: Demonstração estática de algoritmos de validação e modelagem DDL (sem exposição de regras de negócio internas).

## 🚀 Impacto
Ao adotar esta arquitetura, elimina-se a possibilidade de fraude documental ou emissão clandestina (por meio da exigência de compensação tributária integrada no banco de dados para a modalidade REURB-E) e garante-se proteção criptográfica aos cidadãos na modalidade REURB-S.
