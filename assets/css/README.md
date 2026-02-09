# Guia CSS do Projeto

## Objetivo
Este projeto usa CSS com foco em estudo de arquitetura e consistencia visual:
- SMACSS para organizacao por camadas.
- Design tokens para centralizar valores.
- Escala de espacamento em multiplos de 4 (4pt grid).

## Estrutura de Pastas
- `base/`: fundamentos globais (`reset`, `tokens`, `base`).
- `layout/`: estrutura e posicionamento (`l-*`).
- `module/`: aparencia e comportamento visual de componentes.
- `state/`: estados de interface (`is-*`).

## Ordem de Import (style.css)
1. `base`
2. `layout`
3. `module`
4. `state`

## Convencoes de Classes
- Layout: prefixo `l-` (ex.: `l-header`, `l-banner`).
- Modulos: nome sem prefixo obrigatorio (ex.: `banner`, `nav-link`, `logo`).
- Estado: prefixo `is-` (ex.: `is-hidden`).

## Separacao de Responsabilidade
- `layout`: define estrutura (grid, alinhamento, espacamento, largura, posicionamento).
- `module`: define visual (cor, tipografia, borda, hover).

## Tokens
Arquivo: `base/tokens.css`

- Cores: `--cor-*`
- Texto: `--fonte-*`, `--texto-*`
- Espacamento: `--espaco-*`

Exemplo:
- `--espaco-24` representa 24px (`1.5rem`)

## Regra de Espacamento (4pt)
Use apenas valores baseados em 4:
- `4, 8, 12, 16, 20, 24, ...`

Se precisar ajustar um valor:
1. Tente usar o token mais proximo existente.
2. Se nao houver, adicione novo token em `tokens.css` mantendo o multiplo de 4.
3. Evite valores soltos no modulo/layout.

## Boas Praticas para Evolucao
- Antes de criar classe nova, verifique se ja existe modulo/layout reutilizavel.
- Evite acoplar visual de modulo dentro de arquivo de layout.
- Centralize mudancas de escala (espaco e texto) em `tokens.css`.
