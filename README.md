# 🧪 DESAFIO QA – BEEDOO 2025

---

## 📌 User Story – Módulo de Cadastro de Curso


Como usuário do sistema Beedoo QA Tests, quero cadastrar, visualizar e excluir cursos, para gerenciar minha lista de cursos de forma prática e organizada.

**Decisões tomadas para criação da User Story:**
1. O foco principal foi testar o fluxo essencial do sistema: cadastro, listagem e exclusão de cursos.  
2. Foram criados cenários que cobrem tanto casos de sucesso quanto situações de erro e exceção.  
3. As validações priorizaram os pontos críticos do módulo, como a integridade dos dados, usabilidade (UX) e experiência visual (UI).  
4. Todas as evidências e documentações foram centralizadas neste repositório.

---

## 🧾 Contexto e Links Importantes

O objetivo deste desafio foi identificar falhas, inconsistências e oportunidades de melhoria, assegurando que o sistema seja funcional, acessível e com boa experiência de uso.

### Metodologia de Relatório de Bugs
Os bugs foram registrados em uma **planilha de rastreabilidade**, categorizados como Funcionais, Validação ou UX/UI, com prioridade e descrição detalhada, para garantir fácil entendimento e acompanhamento da equipe de desenvolvimento.


- 🌐 **Ambiente de testes:** [Beedoo QA Tests]([https://creative-sherbet-a51eac.netlify.app/new-course](https://creative-sherbet-a51eac.netlify.app/))  
- 🧩 **Funcionalidade testada:** Cadastro, listagem e exclusão de cursos, além da análise de possíveis melhorias.
   
- 📊 **Planilha de testes e evidências:** [Google Sheets – Casos de Teste](https://docs.google.com/spreadsheets/d/1p4P6JoU_KfYsAUmQN_Yh2jZ-jXsutaq_a8usZl_6sq0/edit?gid=0#gid=0)  
- 📋 **Análise complementar (melhorias sugeridas):** [Google Slides – Melhorias UX/UI](https://docs.google.com/presentation/d/1rXzXwUOrSjRwcPsXm0lXF0YBmyfPYWDphsa67rep4sk/edit?slide=id.g39e52667058_2_76#slide=id.g39e52667058_2_76)  
- 🎥 **Evidência em vídeo (MP4) do fluxo de cadastro:** [Google Drive – Vídeo](https://docs.google.com/videos/d/1pTh3RsM8OSasUQZcugDpZAXW51I4kIoJCwOX_NmWXqw/edit?scene=id.g3394bba2_0_1#scene=id.g3394bba2_0_1)

---

## 🐛 Descrição dos Problemas Identificados

Durante os testes exploratórios e direcionados, foram encontrados os seguintes pontos:

### **Bugs Funcionais**
- Cadastro aceita **datas passadas ou invertidas**.  
- **Exclusão de curso** não executa corretamente.  
- Sistema permite **cadastro com campos obrigatórios vazios**.  
- Campo de **número de vagas aceita valores negativos ou zero**.  

### **Bugs de Validação**
- Campo de **data** aceita anos com mais de quatro dígitos.  
- Campo de **descrição** sem limite de caracteres, provocando quebra no layout.  

### **Bugs Visuais / UX/UI**
- **Layout não se adapta** adequadamente em diferentes tamanhos de tela.  
- **Textos longos** e imagens grandes **desalinhando a interface**.  

**Impacto geral:**  
Esses problemas comprometem a confiabilidade do sistema e a experiência do usuário, podendo gerar cadastros inconsistentes, falhas visuais e dificuldades durante o uso.

---

## 🧭 Metodologias Utilizadas

Para a execução deste desafio, foram utilizadas **duas metodologias complementares**:

### 1️⃣ Testes Manuais Exploratório
- **Descrição:** Testes realizados explorando livremente o sistema, buscando identificar bugs inesperados, problemas de usabilidade e inconsistências visuais.  
- **Justificativa:** Permite descobrir falhas que não são óbvias em casos de teste formais, como layout quebrado, textos longos desalinhando a tela ou comportamento inesperado ao inserir dados inválidos.

### 2️⃣ BDD (Behavior Driven Development)
- **Descrição:** Casos de teste estruturados em formato **Gherkin** (Dado/Quando/Então), descrevendo o comportamento esperado do sistema.  
- **Justificativa:** Facilita o entendimento do fluxo de uso tanto para testadores quanto para desenvolvedores e garante que os testes cobrem cenários de sucesso e de erro de forma clara e rastreável.

---

## 🛠 Soluções e Próximos Passos

### **Correções Funcionais**
- Adicionar validação para **bloquear datas passadas ou invertidas**.  
- Implementar **mensagem de confirmação antes da exclusão** de um curso.  
- Garantir que **campos obrigatórios sejam verificados** antes do envio do formulário.  
- Restringir o campo de vagas para **valores positivos apenas**.  

### **Melhorias de Validação e UX**
- Definir **limite de caracteres** em campos de texto (nome e descrição).  
- Exibir **mensagens de erro visuais e descritivas** para cada campo inválido.  
- Mostrar **preview da imagem** da capa ao inserir a URL.  
- **Desativar o botão “Cadastrar curso”** até que os campos obrigatórios sejam preenchidos.  
- Exibir **feedback pós-envio** (mensagem de sucesso ou redirecionamento automático).  
- Revisar **layout responsivo** para diferentes resoluções de tela.

---

## 🧪 Cenários e Casos de Teste

### **Cenário 1 – Cadastro de curso com sucesso**
**Dado** que o usuário está na tela de "Cadastrar Curso"  
**Quando** ele preenche todos os campos corretamente  
**E** clica no botão "Cadastrar curso"  
**Então** o curso é adicionado à lista  
**E** uma mensagem de sucesso é exibida  

### **Cenário 2 – Campos obrigatórios não preenchidos**
**Dado** que o usuário está na tela de "Cadastrar Curso"  
**Quando** ele não preenche os campos obrigatórios  
**E** tenta cadastrar  
**Então** o sistema exibe uma mensagem de erro  
**E** bloqueia o cadastro  

### **Cenário 3 – Datas inválidas**
**Dado** que a data de início é maior que a data de término  
**Quando** o usuário tenta cadastrar o curso  
**Então** o sistema exibe uma mensagem de erro  
**E** impede o cadastro  

### **Cenário 4 – Número de vagas negativo**
**Dado** que o usuário informa um número de vagas negativo (ex: -5)  
**Quando** tenta cadastrar o curso  
**Então** o sistema exibe uma mensagem de erro  
**E** o cadastro é bloqueado  

---

## 📂 Organização dos Artefatos de Teste

| Tipo | Ferramenta / Local | Descrição | Link |
|------|-------------------|-----------|------|
| Planilha de Casos de Teste | Google Sheets | Todos os cenários de teste detalhados, passo a passo e resultados | [Abrir Planilha](https://docs.google.com/spreadsheets/d/1p4P6JoU_KfYsAUmQN_Yh2jZ-jXsutaq_a8usZl_6sq0/edit?gid=0#gid=0) |
| Evidências em Vídeo | Google Drive | Vídeos MP4 mostrando execução dos testes e bugs encontrados | [Abrir Drive](https://docs.google.com/videos/d/1pTh3RsM8OSasUQZcugDpZAXW51I4kIoJCwOX_NmWXqw/edit?scene=id.g3394bba2_0_1#scene=id.g3394bba2_0_1) |
| Análise de Melhorias | Google Slides | Sugestões de UX/UI e validações para otimizar o módulo | [Abrir Apresentação](https://docs.google.com/presentation/d/1rXzXwUOrSjRwcPsXm0lXF0YBmyfPYWDphsa67rep4sk/edit?slide=id.g39e52667058_2_76#slide=id.g39e52667058_2_76) |

---

## ✅ Resultado Esperado

Ao final do ciclo de testes, espera-se:
- Identificação completa dos bugs e oportunidades de melhoria.  
- Registro claro e rastreável dos cenários de teste.  
- Evidências visuais (vídeos/prints) anexadas ao repositório.  
- Recomendações de correções priorizadas e alinhadas às boas práticas de QA.  

---

**🧠 Conclusão:**  
O módulo de cursos apresenta boa estrutura e funcionalidade no geral, porém requer ajustes em validações, mensagens de feedback e layout responsivo para garantir consistência, usabilidade e robustez no fluxo de cadastro.

**📌 Contato e Networking**

Se quiser entrar em contato, conhecer outros projetos ou trocar ideias:

[LinkedIn] (https://www.linkedin.com/in/joice-paiva96/)

[E-mail] joicepaiva96@gmail.com
