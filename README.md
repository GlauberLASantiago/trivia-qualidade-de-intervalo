# 🎵 Trivia Musical — Escalas e Intervalos

Dois widgets de treinamento de percepção musical embutíveis em qualquer site. Feitos com HTML puro + Web Audio API, sem dependências externas.

---

## Demos

| Widget | O que testa |
|--------|-------------|
| **Trivia de escalas** | Ouve uma escala e identifica o tipo (Maior, Blues, Pentatônica…) |
| **Trivia de intervalos** | Ouve dois sons em sequência e identifica a qualidade do intervalo (maior, menor, justa…) |

---

## Como usar

Cada arquivo é autocontido — basta abrir no navegador.

```bash
# clone o repositório
git clone https://github.com/seu-usuario/trivia-musical.git

# abra qualquer um dos dois arquivos
open trivia-escalas.html
open trivia-intervalos.html
```

Para embutir em um site existente, copie o conteúdo do `<div class="card">` e do `<script>` para dentro da sua página.

---

## Funcionalidades

- **Toca automaticamente** a próxima questão ao clicar em "outro →"
- **Botão compartilhar** — gera um `.html` idêntico para enviar por WhatsApp, e-mail ou qualquer canal
- **Clone infinito** — o arquivo gerado também tem o botão de compartilhar
- **Sem servidor** — funciona 100% offline, direto no navegador
- Compatível com todos os navegadores modernos (Chrome, Firefox, Safari, Edge)

---

## Escalas cobertas

| Escala | Semitons |
|--------|----------|
| Maior | 0 2 4 5 7 9 11 12 |
| Menor natural | 0 2 3 5 7 8 10 12 |
| Menor harmônica | 0 2 3 5 7 8 11 12 |
| Pentatônica maior | 0 2 4 7 9 12 |
| Pentatônica menor | 0 3 5 7 10 12 |
| Blues | 0 3 5 6 7 10 12 |

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

O som é gerado por síntese FM de 2 operadores via Web Audio API, com os seguintes parâmetros:

```
Carrier ratio:        1
Modulator ratio:      14
Modulation index:     1200 (ataque) → decaimento exponencial em 1s
Volume base:          0.25
Envelope de volume:   attack 10ms · decay 300ms · release suave
```

A cadeia de sinal é:

```
Modulator OSC → ModGain → Carrier.frequency
Carrier OSC   → AmpGain → Destination
```

---

## Estrutura do projeto

```
trivia-escalas.html     # trivia de escalas musicais
trivia-intervalos.html  # trivia de intervalos melódicos
README.md
```

---

## Licença

MIT
