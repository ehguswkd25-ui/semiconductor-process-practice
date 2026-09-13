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

### 트러블슈팅: Seed layer etching 후 Cu가 남아있던 문제

Seed layer etching(공정 7) 단계에서 Cu가 깨끗하게 식각되지 않고 일부 잔여물이 남는 문제가 발생했다.

- **증상**: Ti/Cu etchant 처리를 마쳤는데도 Cu가 완전히 제거되지 않고 특정 부분에 남아있음.
- **원인 추적 방법**: 문제가 발생한 지점(Seed layer etching)에서부터 공정을 거꾸로 거슬러 올라가며 이전 단계들을 하나씩 점검했다.
- **찾아낸 원인**: 3번 공정인 PR strip(Acetone) 단계에서 처리 시간이 부족했던 것이 근본 원인이었다. Acetone 처리가 충분히 이루어지지 않아 PR이 완전히 제거되지 않았고, 이 잔여 PR이 Cu 표면을 가려 etchant가 닿지 못하면서 Seed layer etching 단계에서 Cu가 그대로 남게 되었다.
- **배운 점**: 공정 초반 단계(PR strip)의 작은 시간 부족이 몇 단계 뒤(Seed layer etching)에서야 문제로 드러날 수 있다는 것을 확인했다. 이후 공정에서 이상이 발견되면 바로 앞 단계만 볼 게 아니라, 공정을 역순으로 하나씩 되짚어보는 접근이 원인 파악에 효과적이었다.
- **얻은 점**: 눈앞에서 발생한 문제를 그 공정 하나만의 독립적인 문제로 판단해서는 안 된다는 것을 깨달았다. 반도체 공정은 여러 단계가 순서대로 이어져 있어서, 앞선 공정에서 생긴 문제가 바로 드러나지 않고 몇 단계를 거친 뒤에야 다른 공정의 결과로 나타날 수 있다. 그래서 문제가 발생했을 때는 해당 공정만 보지 않고, 그 전 공정들까지 전체 흐름을 놓고 원인을 찾아야 한다는 것을 배웠다.

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
