# Dicionario de Dados Protheus

10.630 tabelas do dicionario de dados TOTVS Protheus em formato JSON.

## Estrutura

```
tabelas/
  {PREFIXO}/
    {CODIGO}.json     # Definicao completa da tabela
index.json            # Indice com codigo, nome e prefixo de todas as tabelas
```

## Schema JSON

```json
{
  "tabela": "SA1",
  "nome": "Clientes",
  "nome_eng": "Customers",
  "modo": "C",
  "arquivo": "SA1990",
  "campos": [
    {
      "campo": "A1_COD",
      "titulo": "Codigo",
      "tipo": "C",
      "tam": 6,
      "dec": 0,
      "obrig": true,
      "validacao": "...",
      "ini_padrao": "...",
      "combo": "..."
    }
  ],
  "indices": [
    {
      "ordem": "1",
      "chave": "A1_FILIAL+A1_COD+A1_LOJA",
      "descricao": "Codigo + Loja"
    }
  ],
  "gatilhos": [
    {
      "origem": "A1_COD",
      "tipo": "P",
      "seq": "001",
      "destino": "...",
      "regra": "..."
    }
  ],
  "relacionamentos": [
    {
      "dominio": "SA1",
      "expressao_dom": "A1_COD+A1_LOJA",
      "identificador": "080",
      "expressao_ident": ""
    }
  ]
}
```

## Uso via Raw URL

```
https://raw.githubusercontent.com/antoniosdn/protheus-dicionario/main/tabelas/{PREFIX}/{CODE}.json
```

Exemplo: `https://raw.githubusercontent.com/antoniosdn/protheus-dicionario/main/tabelas/S/SA1.json`

## Nota sobre nomes reservados do Windows

As tabelas `CON` e `NUL` usam prefixo `_` no nome do arquivo (`_CON.json`, `_NUL.json`) por serem nomes reservados do Windows. O codigo no index.json permanece sem prefixo.

## Fonte

Dados extraidos de [dicionario.dev.br](https://dicionario.dev.br).
