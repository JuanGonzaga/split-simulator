# ?? Deploy no GitHub Pages - Guia Completo

## ?? **Prepara��o dos Arquivos**

Todos os arquivos j� est�o prontos na pasta `split-simulator/`:

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

### **1. Criar Reposit�rio**
```bash
# No terminal, na pasta split-simulator/
git init
git add .
git commit -m "?? Initial commit: SPLIT Simulator completo"

# Criar reposit�rio no GitHub com o nome: split-simulator
# Depois conectar:
git remote add origin https://github.com/SEU_USUARIO/split-simulator.git
git branch -M main
git push -u origin main
```

### **2. Ativar GitHub Pages**
1. Ir para **Settings** do reposit�rio
2. Scroll at� **Pages** (menu lateral)
3. **Source:** Deploy from branch
4. **Branch:** main / (root)
5. Clicar **Save**

?? **Aguarde 2-5 minutos** para o deploy autom�tico.

## ?? **URLs de Acesso**

Seu simulador ficar� dispon�vel em:
```
https://SEU_USUARIO.github.io/split-simulator/
```

**Exemplo:**
```
https://juanyurigonzaga.github.io/split-simulator/
```

## ? **Valida��o do Deploy**

### **Checklist P�s-Deploy**
- [ ] Site carrega sem erro 404
- [ ] Fluxograma aparece no topo
- [ ] Bot�es respondem corretamente  
- [ ] Toggles funcionam
- [ ] CSS est� aplicado (cores, layout)
- [ ] Responsivo funciona no mobile

### **Debug Comum**
- **404 Error:** Verifique se `index.html` est� na raiz
- **Styles quebrados:** CDN do Tailwind pode estar bloqueado
- **JS n�o funciona:** Verifique console do browser (F12)

## ?? **Atualiza��es Futuras**

Para atualizar o simulador:
```bash
# Fazer altera��es nos arquivos
git add .
git commit -m "?? Atualiza��o: [descri��o da mudan�a]"
git push origin main

# GitHub Pages atualizar� automaticamente
```

## ?? **Exemplo de Comandos Completos**

```bash
cd /Users/juanyurigonzaga/Desktop/split-simulator

# Inicializar Git
git init
git add .
git commit -m "?? SPLIT Simulator - Vers�o 1.0

? Funcionalidades:
- Fluxograma interativo das 7 etapas
- Configura��es cr�ticas do sistema
- Valida��es t�cnicas baseadas no c�digo real
- Sistema de logs detalhado
- Interface responsiva e moderna

?? Pronto para deploy no GitHub Pages!"

# Conectar ao GitHub (substitua SEU_USUARIO)
git remote add origin https://github.com/SEU_USUARIO/split-simulator.git
git branch -M main
git push -u origin main
```

## ?? **Compartilhamento**

Ap�s o deploy, voc� pode compartilhar:

**?? URL Direta**
```
https://seu-usuario.github.io/split-simulator
```

**?? Para Equipe T�cnica**
> Novo simulador SPLIT dispon�vel! 
> Acesse: https://seu-usuario.github.io/split-simulator
> 
> ? Fluxograma visual das 7 etapas
> ? Configura��es cr�ticas test�veis  
> ? Cen�rios de erro simulados
> ? Logs t�cnicos detalhados

**?? Para Stakeholders**
> Simulador t�cnico do SPLIT j� est� no ar! ??
> 
> Link: https://seu-usuario.github.io/split-simulator
> 
> Agora conseguimos simular e debugar o fluxo completo do SPLIT de forma visual e interativa.

## ??? **Customiza��es Futuras**

Ideias para vers�es futuras:
- [ ] Export/Import de cen�rios 
- [ ] Hist�rico de simula��es
- [ ] Integra��o com API real (desenvolvimento)
- [ ] Themes (dark mode)
- [ ] Mais valida��es espec�ficas por vertical

---

**?? Parab�ns! Seu SPLIT Simulator est� pronto para o mundo!** ??
