# Protocolo metodológico — versão inicial

## Pergunta de pesquisa
Quais regiões dos talhões de teca apresentam semelhança espacial e estabilidade temporal de NDVI e EVI?

## Dados
- Polígonos dos talhões fornecidos pelo pesquisador.
- Landsat Collection 2 Level-2 Surface Reflectance para reconstrução histórica.
- Sentinel-2 Surface Reflectance para detalhamento recente, conforme disponibilidade.
- Metadados e identificadores das imagens efetivamente utilizadas.

## Unidades de análise
Cada polígono de talhão será tratado individualmente, mantendo os identificadores originais. As áreas plantadas em anos diferentes não serão agrupadas automaticamente.

## Índices
NDVI = (NIR - Red) / (NIR + Red)

EVI = 2.5 * (NIR - Red) / (NIR + 6 * Red - 7.5 * Blue + 1)

As bandas correspondentes dependem do sensor; a implementação deve documentar o mapeamento exato de bandas e a escala dos dados de reflectância.

## Comparabilidade temporal
Definir uma janela sazonal comparável e critérios de qualidade após examinar a localização e a disponibilidade das cenas. Não calcular estatísticas anuais sem registrar a quantidade de observações válidas.

## Estabilidade
Avaliar média, desvio-padrão e, quando apropriado, coeficiente de variação. Para índices que podem ser próximos de zero, o coeficiente de variação pode ser instável e não deve ser usado isoladamente. Considerar persistência de padrões e análise visual de mapas anuais.

## Zonas homogêneas
Testar classificação não supervisionada em variáveis padronizadas, documentando o número de classes, semente aleatória, variáveis e avaliação dos resultados. Confirmar as zonas por inspeção visual e, se disponíveis, dados de campo. Não afirmar homogeneidade estrutural da floresta somente a partir de índices espectrais.

## Controle de qualidade e reprodutibilidade
Guardar a data de execução, versão das bibliotecas, coleção, filtros, bandas, resolução, projeção, parâmetros e estatísticas de pixels válidos. Registrar exclusões e limitações.
