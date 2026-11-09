# Como contribuir

Valeu por querer ajudar! O Teclado RGB é um projeto pequeno da comunidade, e toda ajuda conta.

## A contribuição mais útil: testar no seu notebook

Abra uma issue usando o formulário **"Testei no meu notebook"**, mesmo se funcionou de primeira. Cada modelo confirmado entra na tabela do README e ajuda a próxima pessoa a ter confiança para instalar.

## Encontrou um problema?

Abra uma issue usando o formulário **"Problema no app ou no instalador"**, com a saída do terminal.

Falhas de segurança **não** devem ir para issue pública. Veja a [política de segurança](SECURITY.md).

## Enviando um pull request

1. Faça um fork, crie uma branch e faça a sua mudança.
2. **Teste num notebook real**: rode o `./install.sh` até o "Pronto!" e confira se o app troca a cor. O instalador mexe no kernel e roda como root, então mudanças sem teste em hardware real não entram.
3. Se a mudança libera um modelo ou uma CPU nova, adicione o notebook na tabela de testados do README.
4. Abra o PR e preencha o template, dizendo em qual notebook testou.

Os PRs entram na `main` por rebase ou squash, para manter o histórico linear.

## Regras do projeto

- **O driver da TUXEDO não é copiado para cá.** O `install.sh` baixa o [tuxedo-drivers](https://github.com/tuxedocomputers/tuxedo-drivers) num commit fixo (`DRIVER_REF`). Para atualizar a versão do driver, mude o `DRIVER_REF` e teste de novo em hardware real.
- **Ajustes no driver são feitos no próprio `install.sh`**, por exemplo com `sed` sobre uma linha âncora, logo depois de baixar o código. Se a âncora sumir numa versão nova do driver, o ajuste precisa ser revisto.
- **O instalador precisa falhar com uma mensagem clara**, explicando o que aconteceu e o que fazer. Nunca deve falhar em silêncio.
- **Textos para o usuário ficam em português**: README, mensagens do instalador e interface do app.

## Rodando o app sem instalar

```bash
python3 teclado-rgb.py
```

O app precisa do driver carregado e da permissão de escrita no LED. Sem isso ele abre, mas mostra um aviso.
