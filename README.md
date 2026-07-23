# Classificação de Doenças em Folhas de Cana-de-Açúcar utilizando Redes Neurais Convolucionais: Confiabilidade e Generalização

Trabalho de Conclusão de Curso (TCC), Universidade Federal de Campina Grande (UFCG)

**Autor:** Pedro Henrique Sarmento Pereira
**Orientador:** Carlos Eduardo Santos Pires

## Sobre o trabalho

Este projeto avalia três arquiteturas de redes neurais convolucionais (EfficientNet-B0, ResNet50 e MobileNetV3) na classificação de doenças em folhas de cana-de-açúcar.

Além do desempenho tradicional (acurácia, precisão, recall, F1-score), o trabalho investiga se esse desempenho é **confiável**, por meio de:

- Remoção de duplicatas exatas e quase duplicatas
- Divisão dos dados por grupos (evitando vazamento entre treino/validação/teste)
- Diagnóstico de viés de captura (um classificador simples baseado só em cor e brilho)
- Interpretação visual com Grad-CAM
- Validação externa em duas bases de dados independentes

Os modelos atingiram acurácia próxima de 100% na base principal, mas apresentaram queda expressiva de desempenho (entre 25,63 e 50,26 pontos percentuais) quando testados em imagens de outras fontes, o que reforça a importância de não confiar apenas em métricas internas ao avaliar modelos de visão computacional para uso agrícola real.

## Conteúdo do repositório

| Arquivo | Descrição |
|---|---|
| `tcc-cana-de-acucar` | Notebook completo com todo o pipeline: pré-processamento, treinamento, avaliação, diagnóstico de viés, Grad-CAM e validação externa |
| `LICENSE` | Licença MIT |

## O que precisa para executar

- Google Colab
- Baixar os 3 datasets nos links da seção [Datasets utilizados](#datasets-utilizados) e colocar os arquivos (`.zip` e, no caso do Daphal & Koli, também o `.rar`) em uma pasta no Google Drive
- Ajustar a variável `DATASET_ROOT`, na Seção 1 (Setup) do notebook, para o caminho dessa pasta:

```python
DATASET_ROOT = "/content/drive/MyDrive/SEU_CAMINHO_AQUI"
```

## Estrutura de pastas esperada

Os nomes dos arquivos são fixos no código, então, depois de baixar, renomeie os arquivos exatamente como abaixo antes de colocá-los em `DATASET_ROOT`:

```
DATASET_ROOT/
├── Sugarcane.zip
├── disease_folder.zip
└── daphal_koli_v2.zip
```

No caso do `daphal_koli_v2.zip`, o notebook espera que, ao extrair, exista o seguinte caminho interno:

```
Sugarcane Leaf Disease Dataset/Sugarcane Leaf Disease Dataset.rar
```

Se a estrutura interna do zip vier diferente da origem, ajuste manualmente antes de rodar.

## Datasets utilizados

Os três datasets são públicos e estão disponíveis nos links abaixo. Por questão de direitos autorais e tamanho, os arquivos de imagem não estão incluídos neste repositório.

**1. Sugarcane Disease Dataset** (base principal)
Shikalgar, A., Jadhav, S., Surve, A., Bamane, S., Kamble, A. "Sugarcane Disease Dataset", Mendeley Data, V2, 2024.
DOI: [10.17632/7fbnxcbnhp.2](https://doi.org/10.17632/7fbnxcbnhp.2)

**2. disease Dataset** (validação externa, Roboflow)
IOT. "disease Dataset", Roboflow Universe, 2024.
Link: [universe.roboflow.com/iot-4gxaw/disease-zzxeg](https://universe.roboflow.com/iot-4gxaw/disease-zzxeg)
Licença: CC BY 4.0

**3. Sugarcane Leaf Disease Dataset** (validação externa, Daphal & Koli)
Daphal, S., Koli, S. "Sugarcane Leaf Disease Dataset", Mendeley Data, V1, 2022.
DOI: [10.17632/9424skmnrk.1](https://doi.org/10.17632/9424skmnrk.1)

## Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.
