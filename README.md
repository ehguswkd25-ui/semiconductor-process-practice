# 반도체 8대 공정 실습 (TSV/Bump 공정 기반)

대학 반도체 공정 실습에서 진행한 8대 공정(포토, 식각, 박막 증착, 도금 등) 실습 기록입니다.
Wafer 위에 Hole mask → Hole etching → PR strip → Seed layer 증착 → Mold mask → Electroplating → Seed layer etching → Dicing 순서로 진행된 TSV(Through Silicon Via)/범프(Bump) 형성 공정입니다.

> 본 저장소는 교육 목적의 개인 실습 기록이며, 특정 기업/기관의 저작권이 있는 자료나 내부 문서는 포함하지 않았습니다.

## 공정 순서 (Run Sheet)

| No. | 공정명 | Process recipe | 조건 | Comment |
|---|---|---|---|---|
| 1 | Hole mask 형성 | Oxidation wafer | 4" 웨이퍼, GXR601(4년 3um) | - |
| | | PR coating | Low spin 500rpm 10sec / High spin 1000rpm 40sec | Spin coater |
| | | Soft bake | 100℃, 60sec | Hot plate |
| | | Expose | 4sec (150mJ/cm2) | 38mW/cm2 |
| | | Develop | CT-D1 developer, 35sec | Hot plate |
| | | Inspection | - | Microscope |
| | | Hard bake | 110℃, 2min | Hot plate |
| 2 | Hole etching | SiO2 etching | 450W / 490V / CF4 60sccm / 25mTorr / 210sec | ICP-RIE |
| | | Acetone | 1min / IPA 1min / DI 1min | - |
| 3 | PR strip | Acetone | - | - |
| 4 | Seed layer 증착 | Sputter | Ti 500Å / Cu 2000Å | - |
| 5 | Mold mask layer 형성 | PR coating | AZ 10XT (52cp) — low spin 500rpm 10sec / high spin 3500rpm 40sec / low spin 10sec | Spin coater |
| | | Soft bake | 90℃, 4min | Hot plate |
| | | Expose | 10sec (380mJ/cm2) | 38mW/cm2 |
| | | Develop | AZ340:DI = 1:2, 1min | - |
| | | Inspection | - | Microscope |
| 6 | Electroplating | O2 plasma | Ar:O2 = 8:40sccm, 10분, 50mm/s | - |
| | | Cu electroplating | H2SO4 10%, 30sec | Target: 4um | Plasma bonder |
| 7 | Seed layer etching | Ti etching | 0.3A(104SD), 5min, 40Hz, 40rpm | - |
| | | Cu etching | APCUDI | - |
| | | PR strip | Acetone | - | - |
| 8 | Dicing | Wafer dicing | 30000rpm / 10msec | Blade dicing |

## 사용 장비/재료 요약

- **포토리소그래피**: Spin coater, Hot plate, Mask aligner(노광기), Developer
- **식각(Etching)**: ICP-RIE (건식), 습식 식각 (Ti/Cu etchant)
- **박막 증착**: Sputter (Ti/Cu seed layer)
- **도금**: Cu electroplating (H2SO4 기반)
- **다이싱**: Blade dicing

## 실습 노트 / 배운 점

- (여기에 본인이 느낀 공정별 포인트, 트러블슈팅 경험 등을 채워 넣으면 더 좋은 기록이 됩니다.)

## 실습 사진

각 공정 단계별 결과를 촬영한 사진입니다. ([photos/](photos) 폴더)

| 사진 | 공정 단계 | 설명 |
|---|---|---|
| [01_hole_mask_photo.jpg](photos/01_hole_mask_photo.jpg) | 1. Hole mask 형성 | 웨이퍼에 처음 포토(리소그래피) 진행한 결과 (현미경) |
| [04_seed_layer_deposition.jpg](photos/04_seed_layer_deposition.jpg) | 2~4. Hole etching → Seed layer 증착 | 홀을 식각해 뚫고 그 위에 컨덕터(Seed layer)를 올린 모습 |
| [05_mold_mask_prep.jpg](photos/05_mold_mask_prep.jpg) | 5. Mold mask 형성 (도금 준비) | 전기도금을 위해 웨이퍼를 준비하는 모습 |
| [06_electroplating_result_A.jpg](photos/06_electroplating_result_A.jpg) | 6. Electroplating | 도금 완료 후 모습 |
| [06_electroplating_result_B.jpg](photos/06_electroplating_result_B.jpg) | 6. Electroplating | 도금 완료 근접 사진 |
| [07_seed_layer_etching.jpg](photos/07_seed_layer_etching.jpg) | 7. Seed layer etching | 도금 후 시드층 식각 진행 결과 |
| [08_dicing_result.jpg](photos/08_dicing_result.jpg) | 8. Dicing | 칩 절단 이후 모습 |
| [09_sem_thickness_check.jpg](photos/09_sem_thickness_check.jpg) | 최종 검사 | 칩 완성 후 SEM으로 단면 촬영 (도금 두께 측정) |

---
본 문서는 교육 목적으로 작성되었으며, 실제 공정 조건은 실습 환경에 따라 다를 수 있습니다.
