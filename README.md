# Desafio de Projeto: Engenharia de Prompts para Análise de Feedbacks Bancários

Este repositório contém o resultado do desafio de projeto focado na estruturação de um prompt de Inteligência Artificial para análise de dados de experiência do cliente (CX) em um cenário bancário.

---

## 🧱 Passo 1: Definição da Intenção

*   **O que a IA deve analisar:** Comentários de clientes sobre o fluxo de abertura de conta digital e envio de documentos pelo aplicativo.
*   **Quem vai usar o resultado:** A equipe de Engenharia de Produto e o time de Onboarding Digital.
*   **Qual decisão o resultado deve apoiar:** Identificar falhas técnicas no envio de fotos de documentos (RG/CNH), melhorar as taxas de conversão de novos clientes e reduzir o tempo de aprovação de contas.

### Modelo Preenchido (Intenção)
Quero que a IA analise os comentários de novos usuários sobre o processo de abertura de conta e envio de documentos pelo app para identificar falhas no reconhecimento de imagem, mensagens de erro confusas e gargalos de usabilidade.

O resultado será usado pelo time de Onboarding Digital e Engenharia de Produto para apoiar a correção de bugs no aplicativo e redesenhar o fluxo de captura de documentos.

A entrega deve conter um resumo executivo de alto nível, uma tabela detalhada com os problemas e ações sugeridas, e uma lista com as 3 prioridades críticas de correção.

O resultado será considerado bom se for acionável, mapear claramente os erros técnicos citados pelos usuários e separar falhas do sistema de dúvidas comuns de navegação.

---

## 🧱 Passo 2: Contexto e Restrições

*   **Contexto:** O banco digital lançou uma atualização no sistema de reconhecimento biométrico e validação de documentos de identidade (OCR), e muitos clientes estão relatando travamentos ou recusas injustificadas.
*   **Dados disponíveis:** Uma base contendo: ID do Cliente, Sistema Operacional (iOS/Android), Texto do Feedback, Código do Erro exibido na tela e Nota de Satisfação (1 a 5).

### Modelo Preenchido (Contexto e Restrições)
**Contexto:** Estou trabalhando com feedbacks de clientes bancários relacionados ao fluxo de onboarding digital, especificamente na etapa de captura de foto do documento de identidade e selfie de segurança.

**Dados disponíveis:** A base contém o ID do cliente, sistema operacional do smartphone (Android ou iOS), a versão do app, o texto livre do feedback, a nota de satisfação de 1 a 5 e o código de erro técnico gerado pelo sistema.

**Critérios de análise:** A IA deve classificar os feedbacks por gravidade do problema (Bloqueante, Alto, Médio), tipo de falha (Bug de câmera, Rejeição injustificada de documento, Lentidão no carregamento) e sistema operacional afetado.

**Cuidados e restrições:**
1. Use apenas os dados fornecidos no lote de comentários.
2. Não invente estatísticas, porcentagens ou causas que não estejam descritas explicitamente nos textos.
3. Ignore dados que revelem nomes ou números de documentos sensíveis, caso existam.
4. Se o comentário for ambíguo (ex: "não gostei"), classifique como "Informação Insuficiente para Ação Técnica".
5. Use linguagem executiva, direta e focada em engenharia de software e usabilidade.

---

## 🧱 Passo 3: Prompt Final Estruturado

*Este é o comando definitivo construído a partir das etapas anteriores para ser enviado para a IA de análise.*

```text
Atue como Analista Sênior de Dados de Experiência do Cliente e Engenharia de Produto.

Sua tarefa é analisar a base de feedbacks de clientes sobre o fluxo de abertura de conta digital e validação de documentos para identificar falhas técnicas, gargalos de usabilidade e oportunidades de correção imediata.

Contexto: A análise será utilizada pelo time de Onboarding Digital e Engenharia de Software para priorizar correções no sistema de captura de biometria e OCR (reconhecimento de imagem), visando diminuir a taxa de abandono na abertura de novas contas.

Dados disponíveis: Serão fornecidas linhas de dados contendo [ID do Cliente], [Sistema Operacional], [Versão do App], [Texto do Feedback], [Nota (1-5)] e [Código de Erro].

Instruções de análise:
1. Classifique cada feedback por tipo de falha (ex: Bug na Câmera, Rejeição Inválida, Lentidão, Usabilidade).
2. Categorize a severidade em Bloqueante (o cliente não consegue avançar), Alto (gera muita frustração/tentativas repetidas) ou Médio (dúvida estética ou de fluxo).
3. Agrupe os problemas por Sistema Operacional para identificar se há um bug crônico exclusivo em Android ou iOS.
4. Sugira uma ação técnica ou de design corretiva para cada padrão recorrente encontrado.

Formato da resposta:
- Resumo Executivo: Um parágrafo de até 5 linhas sintetizando a saúde atual do fluxo de onboarding.
- Tabela de Diagnóstico: Colunas contendo [Tipo de Falha], [Sistema Operacional Afetado], [Severidade], [Evidência/Resumo do Sintoma] e [Ação Sugerida].
- Plano de Ação: Uma lista ordenada com as 3 correções mais urgentes que a engenharia deve priorizar.

Restrições:
- Baseie-se estritamente nos dados fornecidos; nunca invente bugs ou assuma causas sem evidência no texto.
- Mantenha total sigilo sobre qualquer dado pessoal exposto por erro do cliente.
- Use tom profissional, técnico e focado em engenharia de produto.
```
