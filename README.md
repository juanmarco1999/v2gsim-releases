# V2GSim — instaladores

V2GSim — Simulação G2V/V2G baseada no Renault Twizy. O simulador calcula a transferência de energia
entre a rede elétrica, o carregador e a bateria de um Renault Twizy, na recarga convencional (G2V) e
em cenários hipotéticos de descarga (V2B e V2G). É um trabalho acadêmico de extensão do
Departamento de Engenharia Elétrica da Universidade de Brasília (ENE-UnB). O código-fonte fica num
repositório privado; este repositório contém apenas os binários publicados.

A mesma interface, com as execuções publicadas no servidor, está em <https://v2g.juanmarcosilva.com/>.

## Arquivos de cada release

- `V2GSim-Setup-<versão>.exe`: instalador para Windows 10/11 de 64 bits (Inno Setup, por usuário,
  sem privilégio de administrador). Requer o Microsoft Edge WebView2 Runtime, que já vem no
  Windows 11;
- `V2GSim-Setup-<versão>.exe.sha256`: SHA-256 do instalador;
- `manifest.json` e `manifest.json.sig`: manifesto da versão, assinado com Ed25519, usado pelo
  atualizador do aplicativo.

O atualizador (Sobre › Atualizações) confere a assinatura do manifesto com a chave pública embutida
no programa antes de ler qualquer campo, e só executa o instalador se o tamanho e o SHA-256
conferirem.

Para conferir o hash manualmente (PowerShell):

```powershell
(Get-FileHash .\V2GSim-Setup-<versão>.exe -Algorithm SHA256).Hash
```

## Licença

Código sob a licença MIT. A marca UnB, o emblema Renault e os modelos de terceiros não estão
cobertos pela licença MIT.
