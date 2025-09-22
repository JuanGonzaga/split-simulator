# SPLIT - Simulador Tecnico Completo

> **Simulador interativo completo do sistema SPLIT para Zend Framework 1**  
> Baseado na investigacao real do codigo. Inclui configuracoes criticas, validacoes tecnicas e cenarios complexos descobertos na analise.

[![GitHub Pages](https://img.shields.io/badge/GitHub-Pages-brightgreen)](https://juangonzaga.github.io/split-simulator/)
![React](https://img.shields.io/badge/React-18-blue)
![TailwindCSS](https://img.shields.io/badge/Tailwind-CSS-06B6D4)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-yellow)

## Visao Geral

Este simulador foi desenvolvido para ajudar engenheiros e analistas tecnicos a entender, debugar e validar o comportamento do sistema **SPLIT** da Superlogica, especialmente em cenarios complexos que envolvem:

- **Validacoes tecnicas** baseadas no codigo real
- **Configuracoes criticas** do sistema 
- **Fluxograma visual** com acompanhamento em tempo real
- **Cenarios de erro** e regras de negocio complexas
- **Logs detalhados** de cada operacao

## Funcionalidades

### Fluxograma Interativo
- **Aba expansivel** no topo com visualizacao completa do processo
- **7 etapas principais:** Proprietario ? Locatario ? Imovel ? Contrato ? Cobranca ? Webhook ? Repasse
- **Status dinamico:** Verde (completo), Vermelho (erro), Cinza (pendente)
- **Conectores visuais** que mostram o fluxo entre etapas

### Configuracoes Criticas
- **`novosplit.ativo`**: Engine novo vs legado (Services_Split_Split vs Helpers_Repasses)
- **`split.semprecriar`**: Forca criacao mesmo em cenarios nao ideais
- **`multisplit.ativo`**: Divisao 80%/20% (proprietario/terceiro)

### Cenarios de Validacao
- **CPF/CNPJ obrigatorio** (`pessoas.travarcpfproprietario`)
- **Garantia ativa** (bloqueia SPLIT)
- **Dados invalidos** (PJBank/bancarios)
- **Valor minimo** (R$ 15,00 hard-coded)
- **Timeout de webhook** (30 segundos)
- **Despesas indevidas** (auditoria ERP x PJBank)

### Sistema de Logs
- **Timeline tecnica** detalhada com timestamp
- **Categorizacao** por cores (info, sucesso, aviso, erro)
- **Rastreamento** de todas as operacoes do sistema

## Stack Tecnica

| Tecnologia | Versao | Proposito |
|------------|--------|-----------|
| **React** | 18 | Interface e gerenciamento de estado |
| **Tailwind CSS** | Latest | Estilizacao responsiva |
| **Babel** | Standalone | Transpilacao JSX no browser |
| **JavaScript** | ES6+ | Logica da aplicacao |

## Estrutura do Projeto

```
split-simulator/
??? index.html          # Estrutura HTML principal
??? style.css           # Estilos customizados
??? script.js           # Logica React completa
??? README.md           # Esta documentacao
??? .gitignore          # Arquivos ignorados pelo Git
```

## Acesso Online

**Site do Simulador:** [https://juangonzaga.github.io/split-simulator/](https://juangonzaga.github.io/split-simulator/)

## Como Usar

### 1. Acompanhamento Visual
- Clique na **aba do fluxograma** no topo
- As etapas mudam de cor conforme voce avanca

### 2. Configuracao de Cenarios
- Use os **toggles laterais** para simular diferentes configuracoes
- **Toggles criticos** impactam diretamente o SPLIT

### 3. Simulacao Passo a Passo
1. **Cadastre** as entidades basicas (Proprietario, Locatario, Imovel)
2. **Configure** taxa de administracao e valor da cobranca
3. **Gere** o contrato com FL_SPLIT_CON=1
4. **Crie** a cobranca e aplique tags SPLIT
5. **Simule** o webhook boleto_liquidado
6. **Processe** o repasse final

### 4. Cenarios de Teste
- **Teste positivo:** Deixe configuracoes padrao
- **Teste de erro:** Ative "Garantia ativa" ou "Dados invalidos"
- **Teste de valor:** Ative "Valor < R$15" e veja o comportamento
- **Teste de timeout:** Ative "Webhook timeout" e veja o erro

## Contexto Tecnico

### Arquivos Reais Mapeados
- **`Services/Cobrancas/Split.php`** - Logica principal do SPLIT
- **`Controllers/HooksController.php`** - Webhooks PJBank
- **`Models/ImobiliariaConf.php`** - Configuracoes que afetam SPLIT

### Tabelas do Banco
- **`<licenca>-001.SPLIT`** - Fonte da verdade (financeiro)
- **`app26_<licenca>-001.SPLIT_*`** - Logs e historico (apps)

### Validacoes Tecnicas
- **Valor minimo:** R$ 15,00 (VALOR_MINIMO_REPASSE)
- **CPF/CNPJ obrigatorio** quando configuracao ativa
- **Conta bancaria valida** no PJBank
- **FL_SPLIT_CON = 1** no contrato
- **Sem garantia ativa** no periodo

## Contribuicao

### Para Desenvolvedores
1. **Fork** o projeto
2. Crie uma **branch** para sua feature
3. **Commit** suas mudancas
4. **Push** para a branch
5. Abra um **Pull Request**

### Para Analistas de Negocio
- Reporte **cenarios nao cobertos** via Issues
- Sugira **novas validacoes** baseadas em casos reais
- Documente **edge cases** descobertos em producao

---

**Desenvolvido pela equipe tecnica da Superlogica**
