# Análise temporal e espacial de NDVI/EVI em talhões de teca

Projeto científico reprodutível para investigar a homogeneidade espacial e a estabilidade temporal de índices de vegetação em 14 polígonos de plantios de teca (*Tectona grandis*), utilizando Landsat para a série histórica e Sentinel-2 para detalhamento recente.

## Situação do projeto

- [x] Estrutura inicial do repositório criada.
- [ ] Conferir metadados e autorização de divulgação dos limites dos talhões.
- [ ] Configurar o Google Earth Engine.
- [ ] Executar controle de qualidade dos polígonos.
- [ ] Processar séries temporais Landsat.
- [ ] Processar composições recentes Sentinel-2.
- [ ] Calcular indicadores de homogeneidade e estabilidade.
- [ ] Validar zonas com inspeção visual e, se possível, dados de campo.

## Grupos informados no shapefile de entrada

| Código do projeto | Ano de plantio | Número de polígonos | Área informada aproximada |
|---|---:|---:|---:|
| B | 2005 | 7 | 206,05 ha |
| C | 2008 | 4 | 166,62 ha |
| A | 2011 | 3 | 54,68 ha |

Esses números são uma conferência preliminar dos atributos do arquivo recebido; revalidar no notebook antes da análise final.

## Estrutura

- `notebooks/`: notebooks executáveis no Google Colab.
- `src/`: funções Python reutilizáveis.
- `data/metadados/`: inventário de dados e metadados autorizados para publicação.
- `data/entrada_privada/`: pasta local para arquivos restritos; não enviar ao GitHub.
- `outputs/`: resultados derivados autorizados para divulgação.
- `docs/`: decisões metodológicas e protocolo de análise.

## Dados e privacidade

**Não publique os shapefiles originais até confirmar que existe autorização explícita para divulgar os limites e a localização das propriedades.** O arquivo ZIP original não foi incluído neste pacote inicial. Dados privados devem permanecer fora do repositório público.

O GitHub não deve ser usado como único backup dos dados. Para rasters grandes, considere armazenamento de objetos ou Git LFS, avaliando limites e custos do plano. Arquivos maiores que 100 MB são bloqueados no Git regular pelo GitHub. Consulte a documentação oficial: https://docs.github.com/en/repositories/working-with-files/managing-large-files/about-large-files-on-github

## Requisitos e execução

O notebook `notebooks/01_validacao_dos_talhoes.ipynb` orienta o upload do ZIP no Colab e valida os polígonos. O notebook de processamento de satélite será adicionado após essa conferência.

É necessário ter uma conta Google com acesso ao Google Earth Engine e configurar um projeto Cloud conforme a documentação oficial: https://developers.google.com/earth-engine/guides/python_install

## Princípios metodológicos

1. Preservar os arquivos de entrada originais sem modificá-los.
2. Registrar coleções, identificadores das imagens, datas, filtros, bandas e parâmetros.
3. Aplicar máscaras de nuvens/sombras e critérios de qualidade documentados.
4. Analisar Landsat como série histórica e Sentinel-2 como detalhamento recente, sem assumir equivalência direta entre sensores.
5. Avaliar estabilidade temporal separadamente da semelhança espacial.
6. Não interpretar NDVI/EVI como medidas diretas de volume de madeira ou biomassa.
7. Guardar as versões dos scripts e documentar alterações relevantes.

## Citação

Preencha `CITATION.cff` com os autores e a referência acadêmica quando esses dados forem definidos.
