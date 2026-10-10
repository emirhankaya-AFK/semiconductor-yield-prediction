# English
## Purpose
A reproducible study of rare manufacturing-failure detection using the real-world UCI SECOM dataset. The project treats the problem as it appears in practice: hundreds of noisy process measurements, missing values, only 6.6% failed units, asymmetric error costs, and temporal distribution shift.

## Verified Features
- Newest 20% of observations locked as a chronological holdout.
- Missingness and constant-column filters learned without seeing the holdout.
- Model selection uses out-of-fold development predictions, not test feedback.
- Decision threshold fixed before test evaluation and targets at least 50% development recall.
- False negatives cost 10 times false positives in the reported operating metric.
- PR-AUC and ROC-AUC include 2,000-sample bootstrap confidence intervals.

## Stack
- Python 3.11 | 3.12
- Package structure: `src/semiconductor_yield/` (data, metrics, modeling)
- Scripts: `scripts/download_data.py`, `scripts/train.py`
- Testing: `pytest`, `ruff`
- Artifacts: `artifacts/` for evaluation evidence
- Workflow: `.github/workflows/ci.yml` for CI checks

## Setup & Usage
```bash
python -m pip install -e ".[dev]"
python scripts/download_data.py
python scripts/train.py
python -m pytest -q
python -m ruff check .
```
Generated files:
- `data/manifest.json`: source URL and archive checksum
- `artifacts/metrics.json`: full split, baseline, test, and confidence-interval results
- `artifacts/test_predictions.csv`: holdout probabilities for independent analysis
- `artifacts/holdout_curves.png`: precision-recall and ROC curves
- `artifacts/model.joblib`: local trained bundle (intentionally excluded from Git)

## Testing
Run the test suite with `python -m pytest -q` and code style checks with `python -m ruff check .`.

## Limitations
- The chronological holdout contains only 314 units and 17 failures, leading to wide uncertainty intervals.
- Feature names are anonymized, so the model cannot provide equipment‑level root causes.
- This study is not a production quality‑control system; deployed use would require monitoring and threshold recalibration.
- The selected alert threshold must be revalidated against real fab economics.

## License
Code is released under the MIT License. The dataset remains under its UCI CC BY 4.0 license.

# Türkçe
## Amaç
Gerçek dünya UCI SECOM veri setini kullanarak nadir üretim hatası tahmini üzerine tekrarlanabilir bir çalışma. Proje, yüzlerce gürültü süreci ölçümü, eksik değerler, yalnızca %6.6 başarısız birim,asimmetrik hata maliyetleri ve zamanel dağılım kaymasıyla gerçekçi bir şekilde problemi ele alır.

## Doğrulanmış Özellikler
- Yeni %20 gözlemi kronolojik tutulmuş test olarak kilitlenir.
- Eksiklik ve sabit-sütun filtreleri tutulmuş teste bakılmadan öğrenilir.
- Model seçimi, test geri bildirimi yerine out-of-fold geliştirme tahminleri kullanır.
- Karar eşiği test değerlendirmeden önce belirlenir ve en az %50 geliştirme recallını hedefler.
- Yanlış negatifler, rapor edilen işletme metriğinde yanlış pozitiflerin 10 katı maliyetiyle sayılır.
- PR-AUC ve ROC-AUC, 2.000 örnek bootstrap güveni aralığı içerir.

## Yığın (Stack)
- Python 3.11 | 3.12
- Paket yapısı: `src/semiconductor_yield/` (data, metrics, modeling)
- Betikler: `scripts/download_data.py`, `scripts/train.py`
- Test: `pytest`, `ruff`
- Sanatlar: `artifacts/` için değerlendirme kanıtı
- İş akışı: `.github/workflows/ci.yml` CI kontrolleri

## Kurulum & Kullanım
```bash
python -m pip install -e ".[dev]"
python scripts/download_data.py
python scripts/train.py
python -m pytest -q
python -m ruff check .
```
Oluşturulan dosyalar:
- `data/manifest.json`: kaynak URL ve arşiv toplamı
- `artifacts/metrics.json`: tam bölme, bazen, test ve güven aralığı sonuçları
- `artifacts/test_predictions.csv`: tutulmuş olasılıklar bağımsız analiz için
- `artifacts/holdout_curves.png`: precision-recall ve ROC eğrileri
- `artifacts/model.joblib`: yerel eğitilmiş paket (Git’ten tahriç edilmiştir)

## Test
Test paketini `python -m pytest -q` ile çalıştırın ve kod stilini `python -m ruff check .` ile denetleyin.

## Sınırlamalar
- Kronolojik tutulmuş test yalnızca 314 birim ve 17 başarısızlık içerir, bu da geniş güven aralıklarına yol açar.
- Özellik isimleri anonimleştirildiği için model ekipman‑kök nedeni sağlayamaz.
- Bu çalışma bir üretim kalite kontrol sistemi değildir; dağıtımda izleme ve eşik yeniden kalibrasyonu gerekir.
- Seçilen uyarı eşiği gerçek fab ekonomisine göre yeniden doğrulanmalıdır.

## Lisans
Kod MIT Lisansı altında yayınlanmıştır. Veri seti UCI CC BY 4.0 lisansı altında kalır.

# Deutsch
## Zweck
Eine reproduzierbare Studie zur Erkennung seltener Fertigungsausfälle anhand des realen UCI SECOM-Datensatzes. Das Projekt behandelt das Problem so, wie es in der Praxis auftritt: Hunderte rauschhafte Prozessmesswerte, fehlende Werte, nur 6,6 % ausgefallene Einheiten, asymmetrische Fehlerkosten und zeitliche Verteilungsschiebung.

## Verifizierte Eigenschaften
- Die neuesten 20 % der Beobachtungen werden als chronologischer Holdout gesperrt.
- Fehlende‑ und Konstantenspalten‑Filter werden ohne Einblick in den Holdout gelernt.
- Die Modellselektion nutzt Out‑of‑Fold‑Entwicklungsvorhersagen, nicht Test‑Feedback.
- Der Entscheidungsschwellenwert wird vor der Testauswertung festgelegt und zielt auf mindestens 50 % Entwicklungs‑Recall ab.
- Falsch‑Negative kosten im berichteten Betriebsmetrik das 10‑fache von Falsch‑Positiven.
- PR‑AUC und ROC‑AUC umfassen Konfidenzintervalle aus 2.000‑Sample‑Bootstrap.

## Stack
- Python 3.11 | 3.12
- Paketstruktur: `src/semiconductor_yield/` (data, metrics, modeling)
- Skripte: `scripts/download_data.py`, `scripts/train.py`
- Testen: `pytest`, `ruff`
- Artefakte: `artifacts/` für Evaluationsnachweise
- Workflow: `.github/workflows/ci.yml` für CI‑Checks

## Einrichtung & Nutzung
```bash
python -m pip install -e ".[dev]"
python scripts/download_data.py
python scripts/train.py
python -m pytest -q
python -m ruff check .
```
Erzeugte Dateien:
- `data/manifest.json`: Quell‑URL und Archiv‑Checksumme
- `artifacts/metrics.json`: vollständige Aufteilung, Baseline, Testergebnisse und Konfidenzintervalle
- `artifacts/test_predictions.csv`: Holdout‑Wahrscheinlichkeiten für unabhängige Analyse
- `artifacts/holdout_curves.png`: Precision‑Recall‑ und ROC‑Kurven
- `artifacts/model.joblib`: lokal trainiertes Bundle (absichtlich aus Git ausgeschlossen)

## Testen
Führe die Testsuite mit `python -m pytest -q` aus und überprüfe den Code‑Stil mit `python -m ruff check .`.

## Einschränkungen
- Der chronologische Holdout umfasst lediglich 314 Einheiten und 17 Ausfälle, was zu breiten Unsicherheitsintervallen führt.
- Die Merkmalsnamen sind anonymisiert; das Modell kann keine ursächlichen Geräteinformationen liefern.
- Diese Studie ist kein produktionsfähiges Qualitätskontrollsystem; ein Einsatz erfordert Monitoring und Schwellenwert‑Neukalibrierung.
- Der gewählte Alarm‑Schwellenwert muss gegenüber der realen Fab‑Wirtschaft neu validiert werden.

## Lizenz
Der Code steht unter der MIT‑Lizenz. Der Datensatz bleibt unter der Lizenz UCI CC BY 4.0.
