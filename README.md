# Lanchonete - Projeto de exemplo em Java

Este repositório contém um pequeno sistema de lanchonete em Java para demonstrar conceitos básicos: classes de modelo (`Cliente`, `Produto`, `Pedido`, etc.), serviços (`Cozinha`, `Entregador`, `Cardapio`) e persistência simples em arquivo.

## O que foi adicionado
- Formatação e pequenos hardening:
  - `Produto`: preços formatados com 2 casas decimais.
  - `ItemPedido`: usa `BigDecimal.valueOf(quantidade)` para subtotal.
  - `Pedido`: `toString()` melhorado para listar itens; `getItens()` adicionado.
  - `Cardapio`: itens numerados.
- Persistência simples:
  - `PedidoRepository`: salva pedidos em `data/pedidos.txt` quando o pedido for entregue.
- Arquivos úteis:
  - `.gitignore`, `README.md`, `LICENSE`.

## Como compilar e executar (Windows / PowerShell)
1. Abra o PowerShell e vá para a raiz do projeto:

```powershell
cd d:\dowloads\src
```

2. Compile todos os `.java` para a pasta `out`:

```powershell
if (!(Test-Path -Path .\out)) { mkdir out }
javac -d out lanchonete\*.java lanchonete\model\*.java lanchonete\service\*.java lanchonete\enums\*.java
```

3. Execute a aplicação:

```powershell
java -cp out lanchonete.Main
```

Após executar, o arquivo `data/pedidos.txt` será criado com o histórico de pedidos.

## Licença
MIT — veja o `LICENSE` no repositório.

## Próximos passos sugeridos
- Implementar persistência em JSON e reimportar pedidos como objetos Java.
- Adicionar testes unitários (JUnit) para `Pedido` e `PedidoRepository`.
- Adicionar um script de build (Maven/Gradle) e pipeline GitHub Actions para CI.
