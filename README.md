# 🎵 Trivia de intervalos musicais

Widget de treinamento de percepção musical embutível em qualquer site. Feito com HTML puro + Web Audio API, sem dependências externas.

---

## Como usar

O arquivo é autocontido — basta abrir no navegador.

```bash
open trivia-intervalos.html
```

Para embutir em um site existente, copie o conteúdo do `<div class="card">` e do `<script>` para dentro da sua página.

---

## Como funciona

O app toca dois sons em sequência (intervalo melódico) e já revela a família do intervalo — por exemplo, *"Que qualidade de terça é essa?"*. O usuário escolhe entre as opções daquela família (maior ou menor, no caso das terças).

- Clique em **ouvir** para escutar o intervalo
- Escolha a qualidade correta entre as opções
- Após responder, clique em **outro →** para a próxima questão, que toca automaticamente
- O botão **compartilhar** baixa um `.html` idêntico para enviar por WhatsApp, e-mail ou qualquer canal — e o arquivo gerado também tem o botão de compartilhar

---

## Intervalos cobertos

| Família | Qualidades disponíveis |
|---------|----------------------|
| Primeira | justa |
| Segunda | menor · maior |
| Terça | menor · maior |
| Quarta | justa · aumentada |
| Quinta | diminuta · justa · aumentada |
| Sexta | menor · maior · aumentada |
| Sétima | menor · maior |
| Oitava | justa |

---

## Timbre — síntese FM

O som é gerado por síntese FM de 2 operadores via Web Audio API:

```
Carrier ratio:      1
Modulator ratio:    14
Modulation index:   1200 (ataque) → decaimento exponencial em 1s
Volume base:        0.25
```

Cadeia de sinal:

```
Modulator OSC → ModGain → Carrier.frequency
Carrier OSC   → AmpGain → Destination
```

---

## Licença

MIT
