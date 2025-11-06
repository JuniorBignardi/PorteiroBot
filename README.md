# PorteiroBot

## Instalação 

```bash
git clone https://github.com/JuniorBignardi/PorteiroBot.git
```

## 2. Montagem do Dataset

Inicialmente, para a montagem do dataset foram utilizadas imagens de **13 pessoas distintas**:  
- 10 delas utilizadas como classes de **moradores do prédio**,  
- 3 utilizadas na classe **"Pessoas Desconhecidas"**.  

O dataset foi dividido da seguinte forma:
- **60% para treino**,  
- **20% para teste**,  
- **20% para validação**.  

Inicialmente, os dados foram separados de forma estratificada em 80% para treino e 20% para teste.  
Durante a busca de hiperparâmetros, o conjunto de treino foi dividido novamente usando **cross-validation com 4 folds**, garantindo a distribuição final de 60%/20%/20%.  

## 2. Escolha dos Hiperparâmetros

A escolha dos hiperparâmetros foi realizada utilizando o algoritmo **HalvingGridSearchCV**, da biblioteca **Scikit-Learn**.

O HalvingGridSearch realiza a busca de hiperparâmetros por meio da **redução sucessiva de candidatos**, conforme aumenta o uso de recursos, sendo mais eficiente e menos custoso computacionalmente que o GridSearchCV tradicional.

Todos os hiperparâmetros foram avaliados com **cross-validation de 4 folds**, mantendo a divisão 60%/20%/20%.

### Tabela 2 – Hiperparâmetros e valores considerados na busca

| Hiperparâmetro | Valores Testados |
|----------------|------------------|
| `weights` | `['uniform', 'distance']` |
| `n_neighbors` | `[3, 5, 7, ..., 99]` |
| `metric` | `[None, 'cosine', 'euclidean', 'minkowski']` |
| `p` | `[1, 2]` |

---

