# 🚀 Tina Ponto (Showcase)
**SaaS Multi-Tenant de Gestão de Ponto e RH**

> ⚠️ **Nota:** Este é um repositório de portfólio (Showcase). Como o Tina Ponto é um produto comercial em vias de lançamento para assinaturas, o código-fonte original é mantido em um repositório privado para proteger a propriedade intelectual. Abaixo, detalho toda a arquitetura, regras de negócio e stack tecnológica do projeto. Estou à disposição para apresentar o código em entrevistas técnicas.

---

## 📖 Resumo Executivo
O Tina Ponto é uma plataforma SaaS completa para gestão de controle de ponto, cálculo dinâmico de folha de pagamento e banco de horas. Nascido da necessidade real de automatizar a gestão de equipes na área da gastronomia, o sistema evoluiu para uma arquitetura B2B escalável (Multi-Tenant). 

Ele permite que diferentes empresas se cadastrem de forma autônoma (Self-Service Onboarding), gerenciem seus próprios colaboradores em ambientes isolados e automatizem o fechamento financeiro no fim do mês.

## 💻 Stack Tecnológico
- **Front-end:** Next.js (App Router), React, TypeScript, Tailwind CSS, Lucide Icons.
- **Back-end & Banco de Dados:** Supabase (PostgreSQL), Edge Functions/APIs Serverless.
- **Autenticação e Segurança:** Supabase Auth, Row Level Security (RLS) avançado.
- **Relatórios:** jsPDF, jspdf-autotable (geração no lado do cliente).
- **Mobile:** PWA (Progressive Web App) com Service Workers (sw.js).

## 🏗️ Arquitetura e Módulos Principais

### 1. Motor SaaS Multi-Tenant e Onboarding
- **Self-Service Onboarding:** Fluxo automatizado onde o cliente cria a conta, a API orquestra a geração do banco da empresa e atribui o cargo de "Dono" com 7 dias de Trial automático.
- **Isolamento de Dados (RLS):** Engenharia de banco de dados que garante que gestores de uma empresa jamais tenham acesso aos dados de outra, tudo blindado diretamente no nível do PostgreSQL.
- **Gestão de Acessos:** Sistema de convites para adicionar novos Gestores vinculando o `auth_user_id` de forma segura.

### 2. Motor Contábil e Financeiro (O "Cérebro")
- **Cálculo Condicional Avançado:** Algoritmo que varre todas as batidas do mês, subtrai a matriz esperada e gera saldos em minutos.
- **Modelos de Negócio Variáveis:** Suporte nativo para **Horistas Puros** (pagamento exato por hora trabalhada) ou **Mensalistas CLT** (cálculo de % sobre horas extras e descontos de faltas).
- **Exportação Oficial:** Geração automática de um PDF detalhado com o extrato turno a turno e valor líquido final para assinatura do colaborador.

### 3. Interface do Colaborador (PWA)
- Aplicativo leve e responsivo focado em usabilidade móvel.
- **Validação Biométrica:** Preparado para registro de ponto com reconhecimento facial, garantindo segurança contra fraudes.
- Lançamento manual com justificativas e visualização transparente de saldos.

---

## 📸 Demonstração do Produto
*(Adicione aqui um link para um vídeo curto no Loom mostrando você navegando no sistema, ou insira 3 a 4 screenshots das telas principais: Dashboard, Fechamento de Folha, Tela do App Mobile)*

---
**Desenvolvido por:** [Patrick Fiuza Alves](https://github.com/codetrick95)
