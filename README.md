# 🔧 Página de Manutenção - RN Visita

Página standalone HTML para exibir durante manutenções do sistema RN Visita. Design moderno, responsivo e com verificação automática para detectar quando o sistema volta ao ar.

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![Bootstrap](https://img.shields.io/badge/Bootstrap_5-7952B3?style=flat&logo=bootstrap&logoColor=white)

## ✨ Features

* 🎨 **Design moderno** com glassmorphism e animações suaves
* 📱 **100% responsivo** - funciona perfeitamente em mobile e desktop
* 🔄 **Verificação automática** - detecta quando o sistema voltou e redireciona automaticamente
* ⏱️ **Feedback em tempo real** - mostra quantas verificações já foram feitas
* 🎯 **Zero configuração** - mesma página serve para todas as manutenções
* 🚀 **Ultra leve** - arquivo único de ~6KB
* 🌐 **CDN only** - Bootstrap e ícones via CDN, sem dependências locais

## 🎨 Design

O design segue o style guide do RN Visita com:

* Gradiente azul (`#3a7bd5 → #00d2ff`) no logo e ícone
* Gradiente verde WhatsApp (`#25D366 → #128C7E`) no botão de contato
* Fundo claro com alto contraste para melhor legibilidade
* Animações CSS nativas (ícone girando, barra de progresso, etc)

## 🔄 Como Funciona

A página faz requisições ao site principal (`rntintas.app.br`) a cada 20 segundos. Quando o site volta:

1. Mostra mensagem "Sistema online! Redirecionando..."
2. Aguarda 2 segundos
3. Redireciona automaticamente de volta

Durante a manutenção, exibe:

* Status atual do sistema
* Hora da última verificação
* Contador de tentativas
* Links de contato (email e WhatsApp)

## 🛠️ Stack

* **HTML5** - Estrutura semântica
* **CSS3** - Animações e gradientes nativos
* **JavaScript (Vanilla)** - Verificação com Fetch API
* **Bootstrap 5.3** - Grid e componentes base
* **Bootstrap Icons** - Ícones vetoriais

## 📂 Estrutura

```
manutencao.html     # Arquivo único standalone (6KB)
```

Sim, é só um arquivo. Tudo inline: HTML + CSS + JS.

## 🚀 Deploy

Hospedado no GitHub Pages para disponibilidade 24/7. Durante manutenções no Digital Ocean, o DNS aponta temporariamente para esta página.

## 💡 Decisões Técnicas

**Por que arquivo único?**

* Máxima portabilidade
* Zero dependências de build
* Funciona em qualquer servidor/CDN
* Fácil manutenção

**Por que verificação a cada 20s?**

* Balance entre responsividade e carga no servidor
* Timeout de 5s evita travamento se o servidor estiver lento
* `mode: 'no-cors'` permite verificar sem problemas de CORS

**Por que fundo claro?**

* Melhor legibilidade (contraste 14:1 vs 3:1 do dark)
* Menos cansativo para leitura prolongada
* Mantém identidade visual com acentos azuis

## 📱 Compatibilidade

* ✅ Chrome/Edge 90+
* ✅ Firefox 88+
* ✅ Safari 14+
* ✅ Mobile browsers (iOS/Android)

## 📄 Licença

Projeto pessoal para RN Tintas.

---

**Desenvolvido por Gabriel** | [RN Visita](https://github.com/seu-usuario/rn-visita)
