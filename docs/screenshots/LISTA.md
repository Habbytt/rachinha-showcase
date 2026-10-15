# Capturas para o README

Salve as imagens nesta pasta com **exatamente** estes nomes. O README já aponta para eles.

| Arquivo | Tela | O que precisa aparecer |
|---|---|---|
| `01-hoje.png` | Hoje (painel do dia) | Presença confirmada, times sorteados, partida em andamento e valor a receber |
| `02-sorteio.png` | Sorteio | Times sorteados lado a lado, de preferência com uma dupla travada e alguém na reserva |
| `03-partida.png` | Partidas | Placar em andamento com cronômetro e o histórico de gols e assistências |
| `04-ranking.png` | Ranking | Aba Jogadores com o pódio |
| `05-campeonato.png` | Copas | Liga (todos contra todos) com a classificação e algumas rodadas jogadas |
| `06-financeiro-pix.png` | Financeiro | Lista de quem pagou e quem deve, de preferência com o Pix "copia e cola" gerado |

> ✅ Todas as capturas e o `docs/demo.gif` já foram geradas no simulador do iPhone 16 Pro, com um racha de nomes fictícios e chave Pix fictícia. O GIF mostra Hoje → Sorteio → sortear de novo duas vezes → abrir a partida.
>
> Para refazer, use as instruções abaixo.

## Dicas para as capturas

- Monte um racha de exemplo com **nomes fictícios** (uns 12 a 14 jogadores, para o sorteio ficar bonito).
- Na tela do Pix, use uma **chave fictícia**, nunca sua chave real.
- Tire todas no mesmo aparelho/simulador, em retrato, PNG.
- Verifique se não aparece banner de anúncio de teste. Se aparecer, use uma conta com Pro ativado por código.

## GIF de demonstração (`docs/demo.gif`)

Mostre em **10 a 15 segundos** o fluxo principal, **da lista ao jogo**:

1. Marque a presença de alguns jogadores.
2. Vá em Sorteio e sorteie 2 times.
3. Crie a partida e marque um gol, escolhendo o autor.

Como gravar:

- **Android:** `adb shell screenrecord /sdcard/demo.mp4` (Ctrl+C para parar) e depois `adb pull /sdcard/demo.mp4`.
- **iPhone:** Central de Controle → Gravação de Tela, depois envie o vídeo para o Mac.
- **Simulador iOS:** `xcrun simctl io booted recordVideo demo.mp4` (Ctrl+C para parar).

Converter o vídeo em GIF leve (precisa do `ffmpeg`, `brew install ffmpeg`):

```bash
ffmpeg -i demo.mp4 -vf "fps=12,scale=360:-1:flags=lanczos,split[a][b];[a]palettegen[p];[b][p]paletteuse" -loop 0 docs/demo.gif
```

Tente manter o GIF abaixo de **5 MB** para carregar rápido no GitHub.
