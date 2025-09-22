# ?? SPLIT - Simulador Técnico Completo

> **Simulador interativo completo do sistema SPLIT para Zend Framework 1**  
> Baseado na investigação real do código. Inclui configurações críticas, validações técnicas e cenários complexos descobertos na análise.

![GitHub Pages](https://img.shields.io/badge/GitHub-Pages-brightgreen)
![React](https://img.shields.io/badge/React-18-blue)
![TailwindCSS](https://img.shields.io/badge/Tailwind-CSS-06B6D4)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-yellow)

## ?? **Visão Geral**

Este simulador foi desenvolvido para ajudar engenheiros e analistas técnicos a entender, debugar e validar o comportamento do sistema **SPLIT** da Superlogica, especialmente em cenários complexos que envolvem:

- ? **Validações técnicas** baseadas no código real
- ? **Configurações críticas** do sistema 
- ? **Fluxograma visual** com acompanhamento em tempo real
- ? **Cenários de erro** e regras de negócio complexas
- ? **Logs detalhados** de cada operação

## ?? **Funcionalidades**

### ?? **Fluxograma Interativo**
- **Aba expansível** no topo com visualização completa do processo
- **7 etapas principais:** Proprietário ? Locatário ? Imóvel ? Contrato ? Cobrança ? Webhook ? Repasse
- **Status dinâmico:** ?? Verde (completo), ?? Vermelho (erro), ? Cinza (pendente)
- **Conectores visuais** que mostram o fluxo entre etapas

### ?? **Configurações Críticas**
- **`novosplit.ativo`**: Engine novo vs legado (Services_Split_Split vs Helpers_Repasses)
- **`split.semprecriar`**: Força criação mesmo em cenários não ideais
- **`multisplit.ativo`**: Divisão 80%/20% (proprietário/terceiro)

### ?? **Cenários de Validação**
- **CPF/CNPJ obrigatório** (`pessoas.travarcpfproprietario`)
- **Garantia ativa** (bloqueia SPLIT)
- **Dados inválidos** (PJBank/bancários)
- **Valor mínimo** (R$ 15,00 hard-coded)
- **Timeout de webhook** (30 segundos)
- **Despesas indevidas** (auditoria ERP x PJBank)

### ?? **Sistema de Logs**
- **Timeline técnica** detalhada com timestamp
- **Categorização** por cores (info, sucesso, aviso, erro)
- **Rastreamento** de todas as operações do sistema

## ??? **Stack Técnica**

| Tecnologia | Versão | Propósito |
|------------|--------|-----------|
| **React** | 18 | Interface e gerenciamento de estado |
| **Tailwind CSS** | Latest | Estilização responsiva |
| **Babel** | Standalone | Transpilação JSX no browser |
| **JavaScript** | ES6+ | Lógica da aplicação |

## ?? **Estrutura do Projeto**

```
split-simulator/
??? index.html          # Estrutura HTML básica
??? style.css           # Estilos customizados e animações
??? script.js           # Lógica React completa da aplicação
??? README.md           # Esta documentação
??? .gitignore          # Arquivos ignorados pelo Git
```

## ?? **Deploy e Uso**

### **Acesso Online**
?? **[https://seu-usuario.github.io/split-simulator](https://seu-usuario.github.io/split-simulator)**

### **Execução Local**
```bash
# Clonar o repositório
git clone https://github.com/seu-usuario/split-simulator.git
cd split-simulator

# Abrir no navegador (funciona offline)
open index.html
# ou no VS Code com Live Server
# ou servir via Python: python -m http.server 8000
```

### **GitHub Pages Setup**
1. Push para o branch `main`
2. Vai em **Settings > Pages**
3. Source: **Deploy from branch ? main**
4. O site fica disponível automaticamente

## ?? **Como Usar**

### **1. Acompanhamento Visual**
- Clique na **aba do fluxograma** no topo para acompanhar visualmente
- As etapas mudam de cor conforme você avança no processo

### **2. Configuração de Cenários**
- Use os **toggles laterais** para simular diferentes configurações
- **Toggles críticos** (marcados com ??) impactam diretamente o SPLIT

### **3. Simulação Passo a Passo**
1. **Cadastre** as entidades básicas (Proprietário, Locatário, Imóvel)
2. **Configure** taxa de administração e valor da cobrança
3. **Gere** o contrato com FL_SPLIT_CON=1
4. **Crie** a cobrança e aplique tags SPLIT
5. **Simule** o webhook boleto_liquidado
6. **Processe** o repasse final

### **4. Cenários de Teste**
- **Teste positivo:** Deixe configurações padrão
- **Teste de erro:** Ative "Garantia ativa" ou "Dados inválidos"
- **Teste de valor:** Ative "Valor < R$15" e veja o comportamento
- **Teste de timeout:** Ative "Webhook timeout" e veja o erro

## ?? **Screenshots**

### Fluxograma Expandido
![Fluxograma](https://via.placeholder.com/800x200?text=Fluxograma+Visual+das+7+Etapas)

### Interface Principal
![Interface](https://via.placeholder.com/800x600?text=Interface+Completa+do+Simulador)

## ?? **Contexto Técnico**

### **Arquivos Reais Mapeados**
- **`Services/Cobrancas/Split.php`** - Lógica principal do SPLIT
- **`Controllers/HooksController.php`** - Webhooks PJBank
- **`Models/ImobiliariaConf.php`** - Configurações que afetam SPLIT

### **Tabelas do Banco**
- **`<licenca>-001.SPLIT`** - Fonte da verdade (financeiro)
- **`app26_<licenca>-001.SPLIT_*`** - Logs e histórico (apps)

### **Validações Técnicas**
- ? **Valor mínimo:** R$ 15,00 (VALOR_MINIMO_REPASSE)
- ? **CPF/CNPJ obrigatório** quando configuração ativa
- ? **Conta bancária válida** no PJBank
- ? **FL_SPLIT_CON = 1** no contrato
- ? **Sem garantia ativa** no período

## ?? **Contribuição**

### **Para Desenvolvedores**
1. **Fork** o projeto
2. Crie uma **branch** para sua feature (`git checkout -b feature/nova-funcionalidade`)
3. **Commit** suas mudanças (`git commit -am 'Adiciona nova funcionalidade'`)
4. **Push** para a branch (`git push origin feature/nova-funcionalidade`)
5. Abra um **Pull Request**

### **Para Analistas de Negócio**
- Reporte **cenários não cobertos** via Issues
- Sugira **novas validações** baseadas em casos reais
- Documente **edge cases** descobertos em produção

## ?? **Documentação Adicional**

### **Links Úteis**
- ?? [Documentação Zend Framework 1](https://framework.zend.com/manual/1.12/en/manual.html)
- ?? [Tailwind CSS Docs](https://tailwindcss.com/docs)
- ?? [React 18 Documentation](https://react.dev/)

### **Arquitetura do Sistema**
```
SPLIT Flow:
???????????????    ????????????????    ???????????????
? Proprietário??????   Contrato   ??????  Cobrança   ?
???????????????    ? FL_SPLIT=1   ?    ? + Tag SPLIT ?
                   ????????????????    ???????????????
                           ?                    ?
???????????????    ????????????????    ???????????????
?   Repasse   ??????   Webhook    ??????   PJBank    ?
? (Líquido)   ?    ?boleto_liquidado    ? Liquidação  ?
???????????????    ????????????????    ???????????????
```

## ?? **Licença**

Este projeto é **open source** e está disponível sob a [MIT License](LICENSE).

## ?? **Equipe**

Desenvolvido com ?? pela **equipe técnica da Superlogica**

- ?? **Investigação técnica:** Análise profunda do código Zend 1
- ?? **Design e UX:** Interface intuitiva e responsiva  
- ?? **Deploy e DevOps:** GitHub Pages automático
- ?? **Documentação:** Guias técnicos e de uso

---

## ?? **Suporte**

### **Issues Comuns**
- **Fluxograma não aparece:** Verifique se JavaScript está habilitado
- **Botões não funcionam:** Reload a página, pode ser cache do CDN
- **Styles quebrados:** Verifique conexão com CDN do Tailwind

### **Contato**
- ?? **Bugs:** Abra uma Issue no GitHub
- ?? **Sugestões:** Pull Request ou Discussion
- ?? **Contato direto:** [equipe.tecnica@superlogica.com](mailto:equipe.tecnica@superlogica.com)

---

**? Se este projeto foi útil, deixe uma estrela no GitHub!**
