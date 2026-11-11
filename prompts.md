# 테스트에 쓴 프롬프트

모든 생성에 공통으로 쓴 설정: FLUX.2-klein-4B (GGUF Q4) / 스텝 4 / CFG 4.0 / 시드 42

## 포즈 지시문 (자동으로 앞뒤에 붙음)
- 앞: `The reference image is an OpenPose skeleton (a colored stick figure on a black background). Generate a photo of `
- 뒤: `, in exactly the same full-body pose as the skeleton: match the head direction, both arms and both legs. Do not draw any skeleton lines, colored dots or stick figure; render a natural, realistic scene.`

아래 표의 프롬프트는 앞뒤 지시문 사이에 들어가는 부분입니다.

## 기본 테스트 (단계 8)
| 포즈 | 프롬프트 | 결과 파일 |
|---|---|---|
| pose_01 | a female astronaut in a white spacesuit on the surface of the moon, photorealistic | output_01.png |
| pose_02 | a cute small robot made of shiny metal, 3D cartoon render, plain studio background | output_02.png |
| pose_03 | an old fisherman in a yellow raincoat on a wooden boat, oil painting | output_03.png |

## 실험 A — 같은 포즈(pose_01), 다른 프롬프트 (단계 10)
| # | 프롬프트 | 결과 파일 |
|---|---|---|
| A1 | a female astronaut in a white spacesuit on the surface of the moon, photorealistic | exp_a_01.png |
| A2 | a cute small robot made of shiny metal, 3D cartoon render, plain studio background | exp_a_02.png |
| A3 | an old fisherman in a yellow raincoat on a wooden boat, oil painting | exp_a_03.png |
| 비교 | A1과 같은 프롬프트, **포즈 조건 없음** (지시문도 붙이지 않음) | exp_a_no_pose.png |

## 실험 B — 같은 프롬프트, 다른 포즈 (단계 11)
| # | 포즈 | 프롬프트 | 결과 파일 |
|---|---|---|---|
| B1 | pose_01 | a young man in a red hoodie and blue jeans on a city street at night, photorealistic | exp_b_01.png |
| B2 | pose_02 | (동일) | exp_b_02.png |
| B3 | pose_03 | (동일) | exp_b_03.png |
