# V2GSim — instaladores

Este repositório contém **somente os binários publicados** do V2GSim, simulador do fluxo de potência
entre a rede, o conversor e a bateria de um Renault Twizy (G2V realista e V2G/V2B hipotéticos),
desenvolvido no contexto do IEEE PES UnB / ENE-UnB. O código-fonte é mantido em repositório privado.

Cada release traz:

- `V2GSim-Setup-<versão>.exe` — instalador Windows (Inno Setup, por usuário, sem privilégio de administrador);
- `V2GSim-Setup-<versão>.exe.sha256` — SHA-256 do instalador;
- `manifest.json` e `manifest.json.sig` — manifesto da versão assinado com Ed25519.

O atualizador do aplicativo confere a assinatura do manifesto com a chave pública embutida no
programa **antes** de usar qualquer campo, e só executa o instalador se tamanho e SHA-256 conferirem.

Conferência manual do hash (PowerShell):

```powershell
(Get-FileHash .\V2GSim-Setup-<versão>.exe -Algorithm SHA256).Hash
```

Licença do código: MIT. A marca UnB, o emblema Renault e modelos de terceiros não estão cobertos pela
licença MIT.
