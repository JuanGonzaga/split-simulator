# Deploy no GitHub Pages - Guia Completo

## Preparacao dos Arquivos

Todos os arquivos estao prontos na pasta split-simulator/:

```
split-simulator/
|-- index.html          Pronto
|-- style.css           Pronto  
|-- script.js           Pronto
|-- README.md           Pronto
|-- .gitignore          Pronto
|-- DEPLOY.md           Este arquivo
```

## Setup do GitHub

### 1. Criar Repositorio
```bash
# No terminal, na pasta split-simulator/
git init
git add .
git commit -m "Initial commit: SPLIT Simulator completo"

# Criar repositorio no GitHub com o nome: split-simulator
# Depois conectar:
git remote add origin https://github.com/SEU_USUARIO/split-simulator.git
git branch -M main
git push -u origin main
```

### 2. Ativar GitHub Pages
1. Ir para **Settings** do repositorio
2. Scroll ate **Pages** (menu lateral)
3. **Source:** Deploy from branch
4. **Branch:** main / (root)
5. Clicar **Save**

Aguarde 2-5 minutos para o deploy automatico.

## URLs de Acesso

Seu simulador ficara disponivel em:
```
https://SEU_USUARIO.github.io/split-simulator/
```

**Exemplo:**
```
https://juangonzaga.github.io/split-simulator/
```

## Validacao do Deploy

### Checklist Pos-Deploy
- [ ] Site carrega sem erro 404
- [ ] Fluxograma aparece no topo
- [ ] Botoes respondem corretamente  
- [ ] Toggles funcionam
- [ ] CSS esta aplicado (cores, layout)
- [ ] Responsivo funciona no mobile

### Debug Comum
- **404 Error:** Verifique se index.html esta na raiz
- **Styles quebrados:** CDN do Tailwind pode estar bloqueado
- **JS nao funciona:** Verifique console do browser (F12)

## Atualizacoes Futuras

Para atualizar o simulador:
```bash
# Fazer alteracoes nos arquivos
git add .
git commit -m "Atualizacao: [descricao da mudanca]"
git push origin main

# GitHub Pages atualizara automaticamente
```

## Exemplo de Comandos Completos

```bash
cd /Users/juanyurigonzaga/Desktop/split-simulator

# Inicializar Git
git init
git add .
git commit -m "SPLIT Simulator - Versao 1.0

Funcionalidades:
- Fluxograma interativo das 7 etapas
- Configuracoes criticas do sistema
- Validacoes tecnicas baseadas no codigo real
- Sistema de logs detalhado
- Interface responsiva e moderna

Pronto para deploy no GitHub Pages!"

# Conectar ao GitHub (substitua SEU_USUARIO)
git remote add origin https://github.com/SEU_USUARIO/split-simulator.git
git branch -M main
git push -u origin main
```

## Compartilhamento

Apos o deploy, voce pode compartilhar:

**URL Direta**
```
https://seu-usuario.github.io/split-simulator
```

**Para Equipe Tecnica**
> Novo simulador SPLIT disponivel! 
> Acesse: https://seu-usuario.github.io/split-simulator
> 
> Fluxograma visual das 7 etapas
> Configuracoes criticas testaveis  
> Cenarios de erro simulados
> Logs tecnicos detalhados

**Para Stakeholders**
> Simulador tecnico do SPLIT ja esta no ar!
> 
> Link: https://seu-usuario.github.io/split-simulator
> 
> Agora conseguimos simular e debugar o fluxo completo do SPLIT de forma visual e interativa.

## Customizacoes Futuras

Ideias para versoes futuras:
- [ ] Export/Import de cenarios 
- [ ] Historico de simulacoes
- [ ] Integracao com API real (desenvolvimento)
- [ ] Themes (dark mode)
- [ ] Mais validacoes especificas por vertical

---

**Parabens! Seu SPLIT Simulator esta pronto para o mundo!**