# REPRODUCIBILITY

## Минимальный сценарий запуска (Colab)
1) Откройте notebook:
   notebooks/Aero_space_competition.ipynb

2) Загрузите исходные CSV EOG (2012-2019) в /content/:
   - eog_global_flare_survey_2012_flare_list.csv
   - eog_global_flare_survey_2012_country_summary.csv
   ...
   - eog_global_flare_survey_2019_flare_list.csv
   - eog_global_flare_survey_2019_country_summary.csv

3) Запустите ячейки сверху вниз без пропусков.
   Все результаты сохраняются в папку outputs/.

## Быстрая проверка результата
После выполнения должны существовать:
- outputs/ca3_flaring_watch_map_ru.html
- outputs/alerts_sites_top50_ca3.csv
- outputs/k_selection_silhouette_ca3.png
- outputs/k_selection_davies_bouldin_ca3.png
