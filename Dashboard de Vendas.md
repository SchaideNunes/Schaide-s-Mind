# 📊 Dashboard de Vendas (CRM)

> [!TIP] Dica: Instale o plugin "Dataview"
> Para que as tabelas automáticas abaixo funcionem, você precisa instalar o plugin da comunidade chamado **Dataview**. 
> Vá em Configurações (engrenagem) > Plugins não oficiais (Community plugins) > Buscar > "Dataview" > Instalar e Ativar.

Este painel reúne automaticamente todos os seus leads com base no "Status" que está preenchido neles.

---

## 🎯 Todos os Leads por Status

O Obsidian agrupa e lista todos os clientes de acordo com o status atual deles. Para mudar o cliente de lugar, basta abrir a nota dele e alterar o campo `"Status do contato"` (ou `"Contact Status"` nas notas americanas).

```dataview
TABLE WITHOUT ID
  status AS "Status",
  rows.file.link AS "Leads"
FROM "D:\Obsidian Mind\Schaide"
WHERE contains(tags, "lead")
FLATTEN choice(row["Status do contato"], row["Status do contato"], row["Contact Status"]) AS status
GROUP BY status
SORT status ASC
```

---

## 📋 Lista Detalhada

Aqui você consegue ver uma visão geral de todos os contatos com telefones e emails, facilitando na hora de prospectar.

```dataview
TABLE 
  choice(row["Telefone/WhatsApp"], row["Telefone/WhatsApp"], row["Phone/Text"]) AS "Telefone",
  choice(row["E-mail"], row["E-mail"], row["Email"]) AS "E-mail",
  choice(row["Status do contato"], row["Status do contato"], row["Contact Status"]) AS "Status"
FROM "D:\Obsidian Mind\Schaide"
WHERE contains(tags, "lead")
SORT file.name ASC
```

---

## 🚀 Como gerenciar manualmente (Sem Dataview)

Caso não queira usar plugins, o Obsidian já possui ótimas formas nativas de organizar:

1. **Usando a Busca (Lupa)**: 
   - Pesquise por `"Status do contato": "Não iniciado"` para ver todos os que faltam ligar.
   - Pesquise por `"Status do contato": "Em negociação"` para focar nos clientes quentes.
2. **Propriedades (Properties)**:
   - Toda nota tem um cabeçalho (Frontmatter). O Obsidian possui uma interface nativa onde você pode simplesmente clicar no valor do "Status" e digitar um novo, organizando seu funil de vendas facilmente.
3. **Plugins Alternativos (Kanban)**:
   - Outra opção incrível é instalar o plugin **Kanban**. Com ele, você pode criar um quadro tipo Trello e arrastar as notas dos clientes entre as colunas "Pendente", "Em contato", "Fechou" e "Não respondeu".
