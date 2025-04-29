# Diagrama de Classes - Plataforma de Ensino Online (Preparatório ENEM)

---

## Objetivo do Sistema
Plataforma online de ensino focada no ENEM, com recursos como vídeos curtos, provas online, chat com professores, sistema de notas, entrega de trabalhos e recomendações personalizadas via IA.

---

## Classes Principais

### 1. **Usuário**
**Atributos:**
- id: int  
- nome: string  
- email: string  
- senha: string  
- tipo: enum {Aluno, Professor, Administrador}

**Métodos:**
- fazerLogin()  
- editarPerfil()  
- enviarMensagem()  
- gerarRelatorio()  
- visualizarProgresso()

---

### 2. **Aluno** (herda de Usuário)
**Atributos:**
- progressoTotal: float  
- boletim: List\<Nota\>

**Métodos:**
- assistirAula(aula)  
- fazerProva(prova)  
- enviarTrabalho(trabalho)  
- visualizarCertificado()  
- gerarEstatisticas()  
- baixarConteudo()

---

### 3. **Professor** (herda de Usuário)
**Atributos:**
- especialidade: string  
- biografia: string

**Métodos:**
- criarAula()  
- enviarTrabalho()  
- corrigirProva()  
- organizarCronograma()  
- enviarMaterial()

---

### 4. **Administrador** (herda de Usuário)
**Atributos:**
- permissões: List\<string\>

**Métodos:**
- gerenciarUsuários()  
- configurarSegurança()  
- gerarRelatóriosGerais()

---

### 5. **Aula**
**Atributos:**
- id: int  
- titulo: string  
- descricao: string  
- videoURL: string  
- professor: Professor

**Métodos:**
- baixarMaterial()  
- assistir()  
- recomendarProva()

---

### 6. **Prova**
**Atributos:**
- id: int  
- titulo: string  
- descricao: string  
- tempoMaximo: int  
- dataDisponivel: Date  
- listaQuestoes: List\<Questao\>

**Métodos:**
- iniciarProva()  
- enviarRespostas()

---

### 7. **Questao**
**Atributos:**
- id: int  
- autor: Professor  
- conteudo: string  
- tipo: enum {objetiva, discursiva}  
- gabarito: string

**Métodos:**
- visualizarResultado()

---

### 8. **Trabalho**
**Atributos:**
- id: int  
- titulo: string  
- descricao: string  
- dataEntrega: Date  
- status: enum {pendente, entregue, corrigido}

**Métodos:**
- enviarTrabalho()  
- baixarArquivo()

---

### 9. **Mensagem**
**Atributos:**
- id: int  
- remetente: Usuario  
- destinatario: Usuario  
- conteudo: string  
- dataEnvio: Date

**Métodos:**
- enviar()  
- responder()

---

### 10. **Relatorio**
**Atributos:**
- id: int  
- titulo: string  
- dados: Map  
- aluno: Aluno

**Métodos:**
- enviarPorEmail()  
- exportarPDF()

---

### 11. **Feedback**
**Atributos:**
- id: int  
- aluno: Aluno  
- texto: string  
- data: Date

**Métodos:**
- enviar()  
- visualizar()

---

### 12. **SistemaIA**
**Atributos:**
- id: int  
- status: boolean  
- pacotesDeRecomendacao: List\<Conteudo\>

**Métodos:**
- realizarRecomendacao()  
- atualizarSugestoes()

---

### 13. **Cronograma**
**Atributos:**
- id: int  
- aluno: Aluno  
- atividades: List\<Atividade\>

**Métodos:**
- adicionarAtividade()  
- visualizarAgenda()

---

### 14. **Resumo**
**Atributos:**
- id: int  
- aula: Aula  
- conteudoResumido: string

**Métodos:**
- visualizarResumo()  
- baixarResumo()

---

### 15. **Certificado**
**Atributos:**
- id: int  
- aluno: Aluno  
- dataEmissao: Date  
- curso: string

**Métodos:**
- gerarPDF()  
- enviarPorEmail()

---

## Observações Técnicas (para engenheiros):
- Suporte a múltiplos servidores e sincronização entre dispositivos  
- Sistema seguro com backups regulares  
- IA integrada para recomendações  
- Download de aulas disponível  
- Suporte a escalabilidade com otimização contínua

---
