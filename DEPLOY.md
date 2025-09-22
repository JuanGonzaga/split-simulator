# ?? Deploy no GitHub Pages - Guia Completo

## ?? **Preparação dos Arquivos**

Todos os arquivos já estão prontos na pasta `split-simulator/`:

```
split-simulator/
??? index.html          ? Pronto
??? style.css           ? Pronto  
??? script.js           ? Pronto
??? README.md           ? Pronto
??? .gitignore          ? Pronto
??? DEPLOY.md           ? Este arquivo
```

## ?? **Setup do GitHub**

### **1. Criar Repositório**
```bash
# No terminal, na pasta split-simulator/
git init
git add .
git commit -m "?? Initial commit: SPLIT Simulator completo"

# Criar repositório no GitHub com o nome: split-simulator
# Depois conectar:
git remote add origin https://github.com/SEU_USUARIO/split-simulator.git
git branch -M main
git push -u origin main
```

### **2. Ativar GitHub Pages**
1. Ir para **Settings** do repositório
2. Scroll até **Pages** (menu lateral)
3. **Source:** Deploy from branch
4. **Branch:** main / (root)
5. Clicar **Save**

?? **Aguarde 2-5 minutos** para o deploy automático.

## ?? **URLs de Acesso**

Seu simulador ficará disponível em:
```
https://SEU_USUARIO.github.io/split-simulator/
```

**Exemplo:**
```
https://juanyurigonzaga.github.io/split-simulator/
```

## ? **Validação do Deploy**

### **Checklist Pós-Deploy**
- [ ] Site carrega sem erro 404
- [ ] Fluxograma aparece no topo
- [ ] Botões respondem corretamente  
- [ ] Toggles funcionam
- [ ] CSS está aplicado (cores, layout)
- [ ] Responsivo funciona no mobile

### **Debug Comum**
- **404 Error:** Verifique se `index.html` está na raiz
- **Styles quebrados:** CDN do Tailwind pode estar bloqueado
- **JS não funciona:** Verifique console do browser (F12)

## ?? **Atualizações Futuras**

Para atualizar o simulador:
```bash
# Fazer alterações nos arquivos
git add .
git commit -m "?? Atualização: [descrição da mudança]"
git push origin main

# GitHub Pages atualizará automaticamente
```

## ?? **Exemplo de Comandos Completos**

```bash
cd /Users/juanyurigonzaga/Desktop/split-simulator

# Inicializar Git
git init
git add .
git commit -m "?? SPLIT Simulator - Versão 1.0

? Funcionalidades:
- Fluxograma interativo das 7 etapas
- Configurações críticas do sistema
- Validações técnicas baseadas no código real
- Sistema de logs detalhado
- Interface responsiva e moderna

?? Pronto para deploy no GitHub Pages!"

# Conectar ao GitHub (substitua SEU_USUARIO)
git remote add origin https://github.com/SEU_USUARIO/split-simulator.git
git branch -M main
git push -u origin main
```

## ?? **Compartilhamento**

Após o deploy, você pode compartilhar:

**?? URL Direta**
```
https://seu-usuario.github.io/split-simulator
```

**?? Para Equipe Técnica**
> Novo simulador SPLIT disponível! 
> Acesse: https://seu-usuario.github.io/split-simulator
> 
> ? Fluxograma visual das 7 etapas
> ? Configurações críticas testáveis  
> ? Cenários de erro simulados
> ? Logs técnicos detalhados

**?? Para Stakeholders**
> Simulador técnico do SPLIT já está no ar! ??
> 
> Link: https://seu-usuario.github.io/split-simulator
> 
> Agora conseguimos simular e debugar o fluxo completo do SPLIT de forma visual e interativa.

## ??? **Customizações Futuras**

Ideias para versões futuras:
- [ ] Export/Import de cenários 
- [ ] Histórico de simulações
- [ ] Integração com API real (desenvolvimento)
- [ ] Themes (dark mode)
- [ ] Mais validações específicas por vertical

---

**?? Parabéns! Seu SPLIT Simulator está pronto para o mundo!** ??
