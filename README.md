# 🔧 Página de Manutenção - RN Visita

Página HTML standalone para exibir durante manutenções do sistema RN Visita.

**✨ Destaque:** Verifica automaticamente se o site principal voltou e redireciona sozinho!

## ✨ Recursos

* **Arquivo único** - HTML + CSS + JS em um só arquivo
* **Zero dependências locais** - Bootstrap e ícones via CDN
* **100% responsivo** - Mobile-first design
* **Verificação automática** - Checa se rntintas.app.br voltou a cada 20s
* **Redirecionamento automático** - Volta pro site quando ele estiver online
* **Zero configuração** - Não precisa editar nada a cada manutenção
* **Animações modernas** - Ícone girando, barra de progresso, gradientes
* **Glassmorphism** - Efeito de vidro fosco moderno

## 🚀 Como Usar

### 1. Deploy no GitHub Pages

```bash
# Criar repositório no GitHub
# Subir o arquivo manutencao.html
# Ativar GitHub Pages nas configurações
# URL vai ficar: https://seunome.github.io/repositorio/manutencao.html
```

### 2. Configurar Digital Ocean

No App Platform, quando precisar fazer manutenção:

1. Pausar o app ou
2. Configurar redirect temporário para a página do GitHub Pages

### 3. Personalizar (Opcional)

#### Mudar URL do site principal

Linha 222:

```javascript
const SITE_URL = 'https://rntintas.app.br';
```

#### Ajustar intervalo de verificação

Linha 223:

```javascript
const CHECK_INTERVAL = 20000; // 20 segundos (em milissegundos)
```

Exemplos:

* `10000` = 10 segundos (mais agressivo)
* `30000` = 30 segundos (mais suave)
* `60000` = 1 minuto (economia de recursos)

## 🔄 Como Funciona a Verificação

1. **Página carrega** → Faz primeira verificação imediatamente
2. **A cada 20s** → Tenta acessar `rntintas.app.br`
3. **Site ainda offline** → Mostra "Sistema em manutenção..." + hora da última checagem
4. **Site voltou** → Mostra "Sistema online! Redirecionando..." + aguarda 2s + redireciona

### Indicadores Visuais

```
🔄 Sistema em manutenção...
   Última verificação: 14:35:22 (15x)
```

Quando o site voltar:

```
✅ Sistema online! Redirecionando...
```

## 🎨 Cores do Projeto

```css
--primary-color: #3A7BD5   /* Azul Reenova */
--secondary-color: #00D2FF /* Azul claro gradiente */
```

## 📱 Responsividade

* **Desktop** : Layout centralizado com efeitos completos
* **Tablet** : Ajustes de espaçamento
* **Mobile** : Compacto, alinhado ao topo, fontes menores

## 🛠️ Troubleshooting

### A página não redireciona automaticamente

**Problema:** CORS ou firewall bloqueando requisições

**Solução:** A página usa `mode: 'no-cors'` que funciona na maioria dos casos. Se não funcionar, você pode:

1. Adicionar um endpoint `/health` no seu site que retorna apenas status 200
2. Mudar a verificação para usar esse endpoint específico

### Quer testar localmente

Abra o arquivo direto no navegador. Ele vai tentar acessar rntintas.app.br e mostrar o comportamento real.

## 📦 Dependências Externas

* Bootstrap 5.3.0 (CDN)
* Bootstrap Icons 1.11.0 (CDN)

Funcionam offline após primeiro carregamento (cache do navegador).

## ⚡ Performance

* **Tamanho** : ~6KB (HTML minificado)
* **Carregamento** : < 1s em 3G
* **Compatibilidade** : Todos navegadores modernos (Chrome, Firefox, Safari, Edge)
* **Consumo** : ~1 requisição a cada 20s (muito leve)

## 📝 Workflow Recomendado

```
1. Site precisa de manutenção
   ↓
2. Pausar/redirecionar no Digital Ocean
   ↓
3. Usuários veem página do GitHub Pages
   ↓
4. Página fica checando automaticamente
   ↓
5. Manutenção termina → reativar no Digital Ocean
   ↓
6. Página detecta site online → redireciona automaticamente
   ↓
7. Usuários voltam pro site sem fazer nada!
```

## ✅ Vantagens Dessa Abordagem

* ✅ **Zero edição de código** - Mesma página serve pra todas manutenções
* ✅ **UX perfeita** - Usuário nem precisa recarregar, volta sozinho
* ✅ **GitHub Pages grátis** - Hospedagem confiável sem custo
* ✅ **Sem dependências** - Não precisa de backend ou API
* ✅ **Feedback visual** - Usuário vê quantas vezes já checou

---

**RN Tintas** - Sistema de Visitas Comerciais
