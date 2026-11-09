# Política de segurança

O instalador roda como root e instala um módulo de kernel, então problemas de segurança são levados a sério.

## Como reportar

**Não abra uma issue pública.** Use o relatório privado do GitHub:

👉 [Reportar uma vulnerabilidade](https://github.com/giordanowt/teclado-rgb-linux/security/advisories/new)

Só o mantenedor vê o relatório. Conte o que encontrou, como reproduzir e qual o impacto.

## O que está no escopo

- `install.sh` e `uninstall.sh`
- O app `teclado-rgb.py`
- A regra udev e os arquivos instalados no sistema

Falhas no driver em si devem ser reportadas para a [TUXEDO Computers](https://github.com/tuxedocomputers/tuxedo-drivers).

## Comportamento conhecido e aceito

A regra udev deixa `brightness` e `multi_intensity` do LED do teclado graváveis por qualquer usuário local (`0666`). É isso que permite trocar a cor sem senha. O efeito se limita à cor e ao brilho do teclado.
