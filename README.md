# Solys — Site Institucional

Site institucional da **Solys Administração & Gestão**, empresa especializada na organização e gestão administrativa de associações de proteção patrimonial mutualista, com sede em Fortaleza – CE.

> Mais do que gestão, uma estrutura sólida para crescer.

## Sobre a Solys

Fundada em 2023 em Fortaleza, a Solys nasceu com o propósito de profissionalizar o setor administrativo das associações de proteção patrimonial mutualista, oferecendo uma operação organizada, transparente e confiável.

- **Missão:** Garantir uma gestão administrativa eficiente, organizada e confiável, contribuindo diretamente para o crescimento das associações.
- **Visão:** Ser referência em gestão administrativa para proteção patrimonial mutualista — reconhecida pela excelência, organização e resultados.
- **Valores:** Responsabilidade, organização, transparência, comprometimento, eficiência e respeito.

### Setores especializados

Implantação & Validação · Atendimento 24h · Gestão de Eventos · Cobrança & Relacionamento · Tecnologia & Sistemas · Jurídico · Rastreamento · Financeiro · Recursos Humanos · Marketing & Digital.

## Stack

- **Laravel 13** (PHP 8.4)
- **Blade** com layout modular e partials por seção
- **CSS/JS estáticos** servidos via `public/`
- **SQLite** (sessions/cache padrão Laravel)
- **Caddy** como servidor web em desenvolvimento (HTTPS automático em `solys.test`)

## Estrutura

```
site-laravel/
├── app/Http/Controllers/SiteController.php   # rota / → método home()
├── routes/web.php
├── public/
│   ├── css/site.css                          # estilos do site
│   ├── js/site.js                            # interações (nav, hero, contadores)
│   └── assets/                               # logos e imagens da marca
└── resources/views/
    ├── layouts/app.blade.php                 # layout principal
    ├── site/home.blade.php                   # composição da home
    └── partials/
        ├── nav.blade.php
        ├── footer.blade.php
        ├── whatsapp.blade.php
        └── sections/
            ├── hero.blade.php
            ├── sobre.blade.php
            ├── origem.blade.php
            ├── historia.blade.php
            ├── estrutura.blade.php
            ├── valores.blade.php
            ├── cultura.blade.php
            ├── diferenciais.blade.php
            ├── compromisso.blade.php
            └── cta.blade.php
```

## Como rodar localmente

```bash
git clone git@github.com:SgroupNacional/solys-site.git
cd solys-site
composer install
cp .env.example .env
php artisan key:generate
php artisan migrate
php artisan serve
```

Acesse: http://127.0.0.1:8000

### Com domínio local (Caddy)

Em ambiente já configurado, o site fica disponível em **https://solys.test** (TLS interno do Caddy).

## Como adicionar uma nova página

1. Crie um método no `SiteController` (ex.: `public function contato()`).
2. Registre a rota em `routes/web.php`.
3. Crie a view em `resources/views/site/` estendendo `layouts.app`.

## Contato

- WhatsApp: [+55 85 99999-9999](https://wa.me/5585999999999)
- E-mail: contato@solysadministracao.com.br
- Instagram: [@solysadministracao](https://instagram.com/solysadministracao)
- Endereço: Av. Bezerra de Menezes, 207 — Farias Brito, Fortaleza – CE, 60325-005

---

© Solys Administração & Gestão. Todos os direitos reservados.
