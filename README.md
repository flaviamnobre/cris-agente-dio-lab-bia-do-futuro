# 🌈 CRIS - Controle, Reserva, Inteligência e Sucesso

> CRIS: Seu Estrategista de Liberdade Financeira  

CRIS é um agente de inteligência artificial desenvolvido para transformar a relação de jovens e adultos com o dinheiro. Unindo empatia e análise de dados, ela/ele atua como uma pessoa mentora que se adequa ao que o usuário se identifica, se sente bem. CRIS é para quem precisa sair do vermelho e aprender a dominar suas finanças de forma natural, ou seja, apredendo a ter um relacionamento muito melhor com o dinheiro.

## 💡 O que (e QUEM) é a/o CRIS?

Controle: Organiza o caos financeiro, priorizando o que realmente importa.

Reserva: Foca na construção de segurança para o futuro, não apenas no pagamento de contas.

Inteligência: Analisa juros, taxas e comportamentos de consumo com precisão técnica.

Sucesso: Define metas realistas para que a liberdade financeira seja alcançada sem fórmulas mágicas.

**Propósito**: Descomplicar o "economês" e oferecer um plano de ataque pragmático contra as dívidas, sem julgamentos, transformando ansiedade financeira em estratégia de crescimento.

**O que CRIS faz:**
- ✅ Ajuda a refletir sobre a relação do usuário com seu dinheiro
- ✅ Explica conceitos financeiros de forma simples
- ✅ Usa dados do cliente como exemplos práticos
- ✅ Responde dúvidas sobre produtos financeiros
- ✅ Analisa padrões de gastos de forma educativa


### 🚫 Limitações Declaradas
> **O que o CRIS NÃO faz:**

* **NÃO faz recomendação de investimento:** A/O CRIS explica conceitos e simula cenários educativos, mas nunca indica onde você deve colocar seu dinheiro (ações, fundos, criptoativos, etc.).
* **NÃO acessa dados sensíveis:** O agente nunca solicitará senhas, códigos de autenticação ou tokens de acesso bancário. O compartilhamento de dados é restrito a extratos ou números brutos para análise de fluxo.
* **NÃO substitui um profissional certificado:** A/O CRIS é um suporte educativo e tecnológico; ele não substitui a consultoria de planejadores financeiros certificados (CFP) ou contadores em casos complexos.
* **NÃO realiza transações financeiras:** O agente não tem permissão para efetuar pagamentos, transferências ou agendamentos em nome do usuário.
* **NÃO oferece aconselhamento jurídico ou tributário:** Questões complexas de herança, processos judiciais de cobrança ou declarações de imposto de renda específicas devem ser tratadas com profissionais dessas áreas.
* **NÃO emite julgamentos de valor:** Por ser focado em diversidade e acolhimento, o agente não critica o estilo de vida ou as escolhas de identidade do usuário, limitando-se a analisar o impacto dessas escolhas no equilíbrio financeiro solicitado.
* **NÃO garante rentabilidade:** Como não recomenda investimentos e foca em educação, o agente não faz promessas de lucros ou retornos financeiros sobre o capital do usuário.


## 🏗️ Arquitetura

```mermaid
flowchart TD
    A[Usuário] --> B[Streamlit]
    B --> C[Ollama - LLM Local]
    C --> D[Base de Conhecimento]
    D --> C
    C --> E[Resposta Educativa]
```

**Stack:**
- Interface: Streamlit
- LLM: Ollama (modelo local `gpt-oss`)
- Dados: JSON/CSV mockados

## 📁 Estrutura do Projeto

```
├── data/                          # Base de conhecimento
│   ├── perfil_investidor.json     # Perfil do cliente
│   ├── transacoes.csv             # Histórico financeiro
│   ├── historico_atendimento.csv  # Interações anteriores
│   └── produtos_financeiros.json  # Produtos para ensino
│
├── docs/                          # Documentação completa
│   ├── 01-documentacao-agente.md  # Caso de uso e persona
│   ├── 02-base-conhecimento.md    # Estratégia de dados
│   ├── 03-prompts.md              # System prompt e exemplos
│   ├── 04-metricas.md             # Avaliação de qualidade
│   └── 05-pitch.md                # Apresentação do projeto
│
└── src/
    └── app.py                     # Aplicação Streamlit
```

## 🚀 Como Executar

### 1. Instalar Ollama

```bash
# Baixar em: ollama.com
ollama pull gpt-oss
ollama serve
```

### 2. Instalar Dependências

```bash
pip install streamlit pandas requests
```

### 3. Rodar o Edu

```bash
streamlit run src/app.py
```

## 🎯 Exemplo de Uso

**Pergunta:** "O que é CDI?"  
**CRIS:** "CDI é uma taxa de referência usada pelos bancos. Quando um investimento rende '100% do CDI', significa que ele acompanha essa taxa. Hoje o CDI está próximo da Selic. Quer que eu explique a diferença entre os dois?"

**Pergunta:** "Onde estou gastando mais?"  
**Edu:** "Olhando suas transações de outubro, sua maior despesa é moradia (R$ 1.380), seguida de alimentação (R$ 570). Juntas, representam quase 80% dos seus gastos. Isso é bem comum! Quer que eu explique algumas estratégias de organização?"

## 📊 Métricas de Avaliação

| Métrica | Objetivo |
|---------|----------|
| **Assertividade** | O agente responde o que foi perguntado? |
| **Segurança** | Evita inventar informações (anti-alucinação)? |
| **Coerência** | A resposta é adequada ao perfil do cliente? |

## 🎬 Diferenciais

- **Diversidade:** Respeito à diversidade, com adaptação ao que o usuário se sente melhor. 
- **Personalização:** Usa os dados do próprio cliente nos exemplos
- **100% Local:** Roda com Ollama, sem enviar dados para APIs externas
- **Educativo:** Foco em ensinar, não em vender produtos
- **Seguro:** Estratégias de anti-alucinação documentadas

## 📝 Documentação Completa

Toda a documentação técnica, estratégias de prompt e casos de teste estão disponíveis na pasta [`docs/`](./docs/).
