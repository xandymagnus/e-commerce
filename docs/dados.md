# Organização de dados

## Dados de usuarios:

---

- Usuario:
    -id (INTEGER, PRIMARY_KEY)
    - nome (STRING)
    - data_nascimento (DATE)
    - email (STRING)
    - senha (STRING)
    - status vip (default=False)
    - status adm (default=False)
- Usuario VIP:
    - herda (Usuario)
    - status VIP (True)
- Admininstrador:
    - herda (Usuario)
    - status adm (True)
    - id_adm (INTEGER, PRIMARY_KEY)

---

## Dados de produtos:

---

- Produtos:
    - id (INTEGER, PRIMARY_KEY)
    - nome (STRING)
    - estoque (INTEGER)
    - descricao (TEXT)
    - tipo_produto (STRING / SELECT)
    - detalhes (ARRAY)
--- 
