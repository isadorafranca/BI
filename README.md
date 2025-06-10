# 🕸️ Web Scraping: Extração de Preços de Produtos - Gocase.com.br

Este projeto tem como objetivo realizar web scraping no site Gocase.com.br, extraindo dados de nomes e preços de produtos disponíveis em suas páginas de listagem (ex: "capas para celular", "acessórios").

# 🧠 Objetivo

Automatizar a coleta de informações sobre produtos da Gocase utilizando Python e armazenar os dados em um arquivo CSV para análise posterior.
🛠️ Tecnologias Utilizadas

    Python 3.x

    requests - para fazer as requisições HTTP

    BeautifulSoup (bs4) - para fazer o parsing do HTML

    csv - para armazenar os dados em arquivo

    re - para tratar strings de preço

    time e random - para pausas entre as requisições e evitar bloqueios

# 🔍 Etapas do Projeto
1. Análise da Estrutura HTML

A análise foi feita utilizando o inspecionar elemento do navegador (F12) para identificar:

    O container de cada produto (ex: <div class="product-card">)

    A tag que contém o nome do produto (ex: <h2 class="product-title">)

    A tag do preço (ex: <span class="product-price">)

    A estrutura de paginação (ex: URLs com ?page=)

Obs: Os seletores CSS podem variar. Verifique a estrutura atual da página caso o script não funcione corretamente.
2. Desenvolvimento do Script (gocase_scraper.py)

O script está estruturado em três partes principais:

    fetch_page(url): faz a requisição HTTP da página.

    parse_products(html): extrai os dados HTML dos produtos.

    scrape_website(base_url, max_pages): percorre páginas e acumula os dados.

    save_to_csv(data, filename): salva os dados coletados em um CSV.

3. Funcionamento do Script

python gocase_scraper.py

O script irá:

    Acessar até 5 páginas da categoria escolhida (configurável)

    Extrair o nome e preço de cada produto

    Armazenar os dados em gocase_produtos.csv

# 📦 Estrutura do Arquivo CSV Gerado
| Nome do Produto | Preço (float) | URL Categoria |
| --------------- | ------------- | ------------- |
| Capa iPhone 13  | 89.90         | https\://...  |
| Suporte Pop     | 34.90         | https\://...  |

# ⚠️ Atenção

    Este projeto é apenas para fins educacionais.

    Sites com carregamento via JavaScript dinâmico exigirão ferramentas como Selenium.

    A Gocase pode alterar sua estrutura HTML, o que exigirá ajustes no script.

# ✅ Boas Práticas

    Respeitar o robots.txt do site.

    Utilizar headers para simular um navegador.

    Inserir pausas aleatórias entre requisições para evitar bloqueio.

👩‍💻 Autora

Desenvolvido por Isadora França
Curso: Banco de Dados
GitHub: @isadorafranca
