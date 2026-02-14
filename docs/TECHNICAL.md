# TECHNICAL (FlareWatch CA3)

## Что делает проект
Проект выполняет анализ спутниковых детекций газовых факелов для Центральной Азии (KAZ, UZB, TKM) за 2012-2019 гг. и формирует:
1) кластеризацию объектов (KMeans, k=3),
2) интерпретируемую шкалу impact (Low/Medium/High),
3) top-alerts (top-50 объектов),
4) интерактивную карту (HTML) со слоями.

## Входные данные
Используются ежегодные CSV-файлы EOG Global Flaring Survey (по годам 2012-2019):
- eog_global_flare_survey_YYYY_flare_list.csv
- eog_global_flare_survey_YYYY_country_summary.csv

Файлы должны быть доступны в среде выполнения (в Colab - в /content/).

## Признаки (features) для кластеризации
Кластеризация выполняется по следующим столбцам (после предобработки):
- flr_volume_log1p
- dtc_freq
- clr_obs
- avg_temp
- ellip

## Выбор k
Для обоснования выбора числа кластеров сохранены метрики:
- silhouette: outputs/k_selection_silhouette_ca3.png
- Davies-Bouldin: outputs/k_selection_davies_bouldin_ca3.png

В MVP выбран k=3, чтобы обеспечить баланс между качеством разделения и интерпретируемостью результата (Low/Medium/High).

## Выходные артефакты
Ключевые файлы:
- outputs/ca3_flaring_watch_map_ru.html - интерактивная карта
- outputs/alerts_sites_top50_ca3.csv - топ-50 alerts
- outputs/features_ca3_with_cluster_and_impact.csv - признаки + cluster + impact_class
