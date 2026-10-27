# Endereços do Brasil (CNEFE 2022)

Arquivos de endereços por estado, para busca de número de casa sem internet no OpenTripper,
feitos a partir do **Cadastro Nacional de Endereços para Fins Estatísticos (CNEFE)** do Censo
Demográfico 2022.

**Fonte: IBGE, CNEFE, Censo Demográfico 2022.**
<https://www.ibge.gov.br/estatisticas/sociais/populacao/38734-cadastro-nacional-de-enderecos-para-fins-estatisticos.html>

Os dados são do IBGE, publicados por ele para livre utilização (Decreto 8.777/2016, art. 4º).
Este repositório só os reorganiza para busca; não acrescenta nem corrige nada. Os endereços são de
2022: ruas abertas depois do censo não estão aqui.

## O que há em cada release

- `addresses-manifest.json`: os estados, com arquivo, tamanho e SHA-256.
- `addresses-br-xx.sqlite.gz`: um banco SQLite por estado, compactado.
  - `streets(id, name, folded, locality, city, lat, lon)`: cada rua uma vez por bairro, com o nome
    como o censo escreve, o bairro, o município e um ponto no meio dela.
  - `numbers(street, number, cep, lat, lon)`: cada número da rua, com o CEP e o ponto do censo.
  - `meta(key, value)`: fonte, estado, data.
  - Coordenadas em milionésimos de grau. Só endereços com número e com ponto posto pelo censo
    (`NV_GEO_COORD` 1 a 4).

Feito por `tools/address-data/build.py` do OpenTripper (GPL-3.0-or-later).

---

House-number files per Brazilian state, for offline address search, made from IBGE's CNEFE
(2022 census). Source: IBGE, CNEFE, Censo Demográfico 2022.
