# CriptoLab

Demonstração interativa, em português, de criptografia e descriptografia de texto no navegador. Abra `index.html` em um navegador moderno ou publique o repositório com GitHub Pages.

## Como funciona

- O texto é convertido em bytes UTF-8, incluindo acentos, emojis e símbolos.
- PBKDF2 com SHA-256 e 310.000 iterações deriva uma chave AES de 256 bits a partir da senha e de um salt aleatório de 16 bytes.
- AES-GCM cifra e autentica os bytes usando um IV aleatório de 12 bytes. A autenticação detecta senha incorreta e alterações no pacote.
- O pacote compartilhável tem o formato `AESGCM1.salt.iv.cifra`; os campos binários são codificados em Base64URL. A senha não é incluída.

O site usa a Web Crypto API do navegador. Para executar criptografia, use um contexto seguro (HTTPS ou localhost). Nenhum texto ou senha é enviado a um servidor. O projeto é educativo: não use senhas reais nem dados sensíveis em uma demonstração.

## Publicar no GitHub Pages

Nas configurações do repositório, abra **Pages**, escolha a publicação a partir da branch `main` e da pasta `/ (root)`. O `index.html` será a página inicial.
