# ?? SPLIT - Simulador T�cnico Completo

> **Simulador interativo completo do sistema SPLIT para Zend Framework 1**  
> Baseado na investiga��o real do c�digo. Inclui configura��es cr�ticas, valida��es t�cnicas e cen�rios complexos descobertos na an�lise.

![GitHub Pages](https://img.shields.io/badge/GitHub-Pages-brightgreen)
![React](https://img.shields.io/badge/React-18-blue)
![TailwindCSS](https://img.shields.io/badge/Tailwind-CSS-06B6D4)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-yellow)

## ?? **Vis�o Geral**

Este simulador foi desenvolvido para ajudar engenheiros e analistas t�cnicos a entender, debugar e validar o comportamento do sistema **SPLIT** da Superlogica, especialmente em cen�rios complexos que envolvem:

- ? **Valida��es t�cnicas** baseadas no c�digo real
- ? **Configura��es cr�ticas** do sistema 
- ? **Fluxograma visual** com acompanhamento em tempo real
- ? **Cen�rios de erro** e regras de neg�cio complexas
- ? **Logs detalhados** de cada opera��o

## ?? **Funcionalidades**

### ?? **Fluxograma Interativo**
- **Aba expans�vel** no topo com visualiza��o completa do processo
- **7 etapas principais:** Propriet�rio ? Locat�rio ? Im�vel ? Contrato ? Cobran�a ? Webhook ? Repasse
- **Status din�mico:** ?? Verde (completo), ?? Vermelho (erro), ? Cinza (pendente)
- **Conectores visuais** que mostram o fluxo entre etapas

### ?? **Configura��es Cr�ticas**
- **`novosplit.ativo`**: Engine novo vs legado (Services_Split_Split vs Helpers_Repasses)
- **`split.semprecriar`**: For�a cria��o mesmo em cen�rios n�o ideais
- **`multisplit.ativo`**: Divis�o 80%/20% (propriet�rio/terceiro)

### ?? **Cen�rios de Valida��o**
- **CPF/CNPJ obrigat�rio** (`pessoas.travarcpfproprietario`)
- **Garantia ativa** (bloqueia SPLIT)
- **Dados inv�lidos** (PJBank/banc�rios)
- **Valor m�nimo** (R$ 15,00 hard-coded)
- **Timeout de webhook** (30 segundos)
- **Despesas indevidas** (auditoria ERP x PJBank)

### ?? **Sistema de Logs**
- **Timeline t�cnica** detalhada com timestamp
- **Categoriza��o** por cores (info, sucesso, aviso, erro)
- **Rastreamento** de todas as opera��es do sistema

## ??? **Stack T�cnica**

| Tecnologia | Vers�o | Prop�sito |
|------------|--------|-----------|
| **React** | 18 | Interface e gerenciamento de estado |
| **Tailwind CSS** | Latest | Estiliza��o responsiva |
| **Babel** | Standalone | Transpila��o JSX no browser |
| **JavaScript** | ES6+ | L�gica da aplica��o |

## ?? **Estrutura do Projeto**

```
split-simulator/
??? index.html          # Estrutura HTML b�sica
??? style.css           # Estilos customizados e anima��es
??? script.js           # L�gica React completa da aplica��o
??? README.md           # Esta documenta��o
??? .gitignore          # Arquivos ignorados pelo Git
```

## ?? **Deploy e Uso**

### **Acesso Online**
?? **[https://seu-usuario.github.io/split-simulator](https://seu-usuario.github.io/split-simulator)**

### **Execu��o Local**
```bash
# Clonar o reposit�rio
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
4. O site fica dispon�vel automaticamente

## ?? **Como Usar**

### **1. Acompanhamento Visual**
- Clique na **aba do fluxograma** no topo para acompanhar visualmente
- As etapas mudam de cor conforme voc� avan�a no processo

### **2. Configura��o de Cen�rios**
- Use os **toggles laterais** para simular diferentes configura��es
- **Toggles cr�ticos** (marcados com ??) impactam diretamente o SPLIT

### **3. Simula��o Passo a Passo**
1. **Cadastre** as entidades b�sicas (Propriet�rio, Locat�rio, Im�vel)
2. **Configure** taxa de administra��o e valor da cobran�a
3. **Gere** o contrato com FL_SPLIT_CON=1
4. **Crie** a cobran�a e aplique tags SPLIT
5. **Simule** o webhook boleto_liquidado
6. **Processe** o repasse final

### **4. Cen�rios de Teste**
- **Teste positivo:** Deixe configura��es padr�o
- **Teste de erro:** Ative "Garantia ativa" ou "Dados inv�lidos"
- **Teste de valor:** Ative "Valor < R$15" e veja o comportamento
- **Teste de timeout:** Ative "Webhook timeout" e veja o erro

## ?? **Screenshots**

### Fluxograma Expandido
![Fluxograma](https://via.placeholder.com/800x200?text=Fluxograma+Visual+das+7+Etapas)

### Interface Principal
![Interface](https://via.placeholder.com/800x600?text=Interface+Completa+do+Simulador)

## ?? **Contexto T�cnico**

### **Arquivos Reais Mapeados**
- **`Services/Cobrancas/Split.php`** - L�gica principal do SPLIT
- **`Controllers/HooksController.php`** - Webhooks PJBank
- **`Models/ImobiliariaConf.php`** - Configura��es que afetam SPLIT

### **Tabelas do Banco**
- **`<licenca>-001.SPLIT`** - Fonte da verdade (financeiro)
- **`app26_<licenca>-001.SPLIT_*`** - Logs e hist�rico (apps)

### **Valida��es T�cnicas**
- ? **Valor m�nimo:** R$ 15,00 (VALOR_MINIMO_REPASSE)
- ? **CPF/CNPJ obrigat�rio** quando configura��o ativa
- ? **Conta banc�ria v�lida** no PJBank
- ? **FL_SPLIT_CON = 1** no contrato
- ? **Sem garantia ativa** no per�odo

## ?? **Contribui��o**

### **Para Desenvolvedores**
1. **Fork** o projeto
2. Crie uma **branch** para sua feature (`git checkout -b feature/nova-funcionalidade`)
3. **Commit** suas mudan�as (`git commit -am 'Adiciona nova funcionalidade'`)
4. **Push** para a branch (`git push origin feature/nova-funcionalidade`)
5. Abra um **Pull Request**

### **Para Analistas de Neg�cio**
- Reporte **cen�rios n�o cobertos** via Issues
- Sugira **novas valida��es** baseadas em casos reais
- Documente **edge cases** descobertos em produ��o

## ?? **Documenta��o Adicional**

### **Links �teis**
- ?? [Documenta��o Zend Framework 1](https://framework.zend.com/manual/1.12/en/manual.html)
- ?? [Tailwind CSS Docs](https://tailwindcss.com/docs)
- ?? [React 18 Documentation](https://react.dev/)

### **Arquitetura do Sistema**
```
SPLIT Flow:
???????????????    ????????????????    ???????????????
? Propriet�rio??????   Contrato   ??????  Cobran�a   ?
???????????????    ? FL_SPLIT=1   ?    ? + Tag SPLIT ?
                   ????????????????    ???????????????
                           ?                    ?
???????????????    ????????????????    ???????????????
?   Repasse   ??????   Webhook    ??????   PJBank    ?
? (L�quido)   ?    ?boleto_liquidado    ? Liquida��o  ?
???????????????    ????????????????    ???????????????
```

## ?? **Licen�a**

Este projeto � **open source** e est� dispon�vel sob a [MIT License](LICENSE).

## ?? **Equipe**

Desenvolvido com ?? pela **equipe t�cnica da Superlogica**

- ?? **Investiga��o t�cnica:** An�lise profunda do c�digo Zend 1
- ?? **Design e UX:** Interface intuitiva e responsiva  
- ?? **Deploy e DevOps:** GitHub Pages autom�tico
- ?? **Documenta��o:** Guias t�cnicos e de uso

---

## ?? **Suporte**

### **Issues Comuns**
- **Fluxograma n�o aparece:** Verifique se JavaScript est� habilitado
- **Bot�es n�o funcionam:** Reload a p�gina, pode ser cache do CDN
- **Styles quebrados:** Verifique conex�o com CDN do Tailwind

### **Contato**
- ?? **Bugs:** Abra uma Issue no GitHub
- ?? **Sugest�es:** Pull Request ou Discussion
- ?? **Contato direto:** [equipe.tecnica@superlogica.com](mailto:equipe.tecnica@superlogica.com)

---

**? Se este projeto foi �til, deixe uma estrela no GitHub!**
