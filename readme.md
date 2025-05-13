# 📦 Prompt de Emissões de Voos com Milhas – Inteligente e Automatizado

Este prompt é usado com o ChatGPT para processar automaticamente dois arquivos CSV de voos de ida e volta exportados do Seats.Aero ou similares.

## ✅ Funcionalidades do Prompt

- Detecta automaticamente os programas de milhas presentes.
- Separa por cabine: Economy, Business, First.
- Gera as 15 melhores combinações válidas por programa e por classe.
- Organiza tudo em estrutura: Companhia > Classe > Arquivos.
- Gera PDF com links de hotéis:
  - Booking.com
  - Hoteis.com
  - Kayak (corrigido)
- Links usam **nome da cidade correspondente ao IATA**, nunca região ou nome do aeroporto.

## 🧠 Prompt completo para usar no ChatGPT

```
IDA_VOLTA_OK

Leia dois arquivos CSV contendo voos de ida e voos de volta.

Regras obrigatórias:
- Considere apenas combinações onde exista efetivamente ida e volta disponíveis, ambas com milhas superiores a zero.
- Duração obrigatória entre 7 e 30 dias.
- Origem e destino obrigatoriamente invertidos (ex: GRU > JFK e JFK > GRU).
- Ida e volta obrigatoriamente com o mesmo programa de milhas.

Processamento automático:
1. Leia os dois arquivos CSV.
2. Detecte automaticamente todos os programas de milhas presentes.
3. Para cada programa detectado:
   - Faça o cruzamento rigoroso dos voos.
   - Separe por cabine (Economy, Business, First).
   - Gere as 15 melhores combinações por programa e por cabine.
4. Organize todos os resultados automaticamente em hierarquia de pastas:
   - Companhia (programa)
     - Economy
     - Business
     - First
   - Dentro de cada pasta, gerar:
     - PDF com as 15 melhores combinações, links de hotéis clicáveis e formatados corretamente.
     - Planilha Excel com as mesmas informações.
5. Geração dos links de hotéis:
   - Use sempre o nome correto da cidade correspondente ao código IATA do destino.
   - NÃO usar região ou nome do aeroporto.
   - Formatos:
     - Booking.com:
       https://www.booking.com/searchresults.pt-br.html?ss=NOME_DA_CIDADE&checkin=AAAA-MM-DD&checkout=AAAA-MM-DD
     - Hoteis.com:
       https://www.hoteis.com/Hotel-Search?destination=NOME_DA_CIDADE%2C%20BR&checkin=AAAA-MM-DD&checkout=AAAA-MM-DD
     - Kayak:
       https://www.kayak.com.br/hotels/NOME_DA_CIDADE,BR/AAAA-MM-DD/AAAA-MM-DD/2adults;map?sort=rank_a
6. Caso alguma cabine ou programa não tenha disponibilidade válida, mostre no relatório com alerta claro.
7. Valide todos os arquivos.
```

---

Criado por: [Seu Nome ou Organização]
