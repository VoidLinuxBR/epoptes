# epoptes

Epoptes (gerenciamento e monitoramento de laboratório de informática) com suporte a Wayland, para VoidBR e Chili Linux.

Um repositório gera **dois pacotes**, como no AUR:

| | Void (`pkgfile/PKGFILE`) | Arch (`pkgbuild/PKGBUILD`) |
|---|---|---|
| Servidor (professor) | `voidbr-epoptes` | `chili-epoptes` |
| Cliente (aluno) | `voidbr-epoptes-client` | `chili-epoptes-client` |

- `usr/` e `etc/`: arquivos originais do Epoptes, servidor e cliente juntos.
- `pkgfile/voidbr-epoptes.patch` (cópia em `pkgbuild/`): as mudanças do VoidBR, aplicadas no `prepare()`.
- Cada `package_*()` leva só a sua parte; as traduções (`usr/share/locale`) vão nos dois.
- No Void precisa do pkgmake 1.12 ou mais novo (pacotes divididos).

## Editar o patch

```sh
./gera-patch.sh aplicar    # aplica o patch na árvore
# edite os arquivos
./gera-patch.sh gerar      # gera o patch novo, troca o sha256 nas duas receitas e limpa a árvore
./gera-patch.sh conferir   # confere patch, cópias e sha256
```

O manual de uso fica em `usr/share/epoptes/LEIAME.md` (menu Ajuda do Epoptes, F1).
