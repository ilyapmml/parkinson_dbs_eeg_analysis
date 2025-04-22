# About project

This study processes neurophysiological data from Parkinson’s disease (PD) patients who underwent Deep Brain Stimulation (DBS) surgery at the Burdenko Neurosurgery Center. PD, a neurodegenerative disorder, affects the basal ganglia, including the subthalamic nucleus (STN), causing motor symptoms like tremor, bradykinesia, and rigidity. The main goal is to examine coherence—signal synchronization—between the motor cortex (EEG channels: CZ, C3, C4) and STN (DBS channels: 1-2, 2-3, 4-3, left/right hemispheres), focusing on the beta range (13–30 Hz), linked to motor impairments in PD.
Coherence measures cortex-STN interaction strength, revealing neural mechanisms of motor deficits and effects of therapies like levodopa and DBS. Beta-band synchronization, modulated by dopamine, positions coherence as a potential biomarker of therapy efficacy. This study uses EEG-DBS data to deepen understanding of cortex-STN interactions, addressing gaps in prior research, and aims to optimize PD therapy through personalized approaches.
Data preprocessing includes:
1. Loading: Raw .fif EEG/DBS signals are loaded via MNE-Python, selecting relevant channels.
2. Filtering and resampling: A 50 Hz notch filter removes noise; data is resampled to 200 Hz.
3. Channel averaging: STN signals (e.g., 1-2A_R, 1-2B_R, 1-2C_R) are averaged (e.g., 1-2_R).
4. Differential signals: Motor channels (e.g., CZ-C3, CZ-C4) are computed.
5. Coherence analysis: Multitaper method quantifies coherence.
6. Power spectral density (PSD): Welch’s method evaluates signal power.
7. Visualization and analysis: Neuroscience-specific plots and statistical analysis explain results.
The pipeline produces preprocessed data, coherence, and PSD in .csv format for analyzing DBS states (ON vs. OFF), levodopa effects, and motor impairment biomarkers. The research enhances understanding of PD neural interactions and supports personalized therapies.


Данная работа посвящена обработке и анализу нейрофизиологических данных, полученных от пациентов с болезнью Паркинсона (БП), которым была проведена операция по установке системы глубокой стимуляции мозга (DBS) в Центре нейрохирургии им. Н. Н. Бурденко. БП — нейродегенеративное заболевание, связанное с нарушением работы базальных ганглиев, включая субталамическое ядро (STN), и проявляющееся моторными симптомами, такими как тремор, брадикинезия и ригидность. Основная цель исследования — изучение когерентности, то есть степени синхронизации сигналов (фазовой связности осцилляций), между моторной корой (каналы ЭЭГ: CZ, C3, C4) и STN (каналы DBS: 1-2, 2-3, 4-3, правого и левого полушарий) в различных частотных диапазонах, с акцентом на бета-диапазон (13–30 Гц), который связан с моторными нарушениями при БП.
Когерентность служит мерой силы взаимодействия между STN и моторной корой, позволяя оценить нейронные механизмы моторных нарушений и влияние терапевтических вмешательств, таких как медикаментозная терапия леводопой (предшественником дофамина) и DBS. Синхронизация в бета-диапазоне зависит от уровня дофамина, и леводопа может её модулировать, что делает когерентность потенциальным биомаркером эффективности терапии и индикатором состояния пациентов. Поскольку существующие исследования не дают полной картины взаимодействия моторной коры и STN, данная работа углубляет понимание этих процессов на выборке пациентов с использованием комбинированных данных ЭЭГ и DBS. Исследование направлено на выявление закономерностей синхронизации, которые могут способствовать оптимизации терапии БП и разработке персонализированных подходов к лечению.
Предобработка данных включает следующие этапы:
1. Загрузка данных: Сырые сигналы ЭЭГ и DBS в формате .fif загружаются с использованием библиотеки MNE-Python, отбираются релевантные каналы (CZ, C3, C4 для ЭЭГ; 1-2A/B/C, 2-3A/B/C, 4-3A/B/C для DBS).
2. Фильтрация и передискретизация: Применяется режекторный фильтр на частоте 50 Гц для устранения сетевых помех, данные передискретизируются до 200 Гц для унификации.
3. Усреднение каналов: Сигналы от групп электродов STN (например, 1-2A_R, 1-2B_R, 1-2C_R) усредняются для получения единого сигнала (например, 1-2_R).
4. Вычисление дифференциальных сигналов: Создаются дифференциальные сигналы для моторных каналов (CZ-C3, CZ-C4).
5. Анализ когерентности: Метод multitaper используется для вычисления когерентности между моторными и STN каналами.
6. Анализ спектральной плотности мощности (PSD): Метод Уэлча применяется для оценки спектральных характеристик сигналов.
7. Выявление других закономерностей и объяснение результатов: Построение специфичных для нейронаук графиков и статистический анализ с последующим объяснением результатов.
Работа создаёт пайплайн для обработки нейроданных. Результаты (предобработанные данные, когерентность, PSD) сохраняются в формате .csv и могут использоваться для сравнения состояний DBS (ON vs. OFF), оценки влияния леводопы и выявления биомаркеров моторных нарушений.


# Project structure

```
parkinson_dbs_eeg_analysis/
├── data/
│   ├── raw/                    # Sample Raw .fif file
│   ├── preprocessed/           # Sample data .csv file
│   ├── coherence/              # Sample Coherence .csv files
│   ├── psd/                    # Sample psd .csv file
├── notebooks/
│   └── compilated_preprocessing.ipynb  # Preprocessing pipeline
├── README.md                   # Project description
```


# Installation

Install the required Python libraries manually:
- `numpy`
- `pandas`
- `mne`
- `mne-connectivity`
- `matplotlib`

```bash
pip install numpy pandas mne mne-connectivity matplotlib