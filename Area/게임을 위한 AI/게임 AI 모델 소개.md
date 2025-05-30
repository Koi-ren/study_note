![[ai모델.jpg|500]]
# 의사코드

본 책에서는 단순함을 위해서 의사 코드(pseudo-code)로 표현
의사 코드는 가상의 프로그래밍 언어로 알고리즘 작동 방식은 설명 가능

# 알고리즘 같아 보이는 것이 게임 AI로 간주되는 이유

단순한 물리 계산이 아니라, 캐릭터가 환경에 반응하며 "스스로 판단한 듯한" 움직임을 보이게 한다. AI의 핵심은 자율성(autonomy)과 환경 적응이다:

- **자율성**: 캐릭터가 목표 위치를 기반으로 스스로 속도와 방향을 결정.
- **환경 적응**: 목표와의 거리(radius)나 속도 제한(maxSpeed)에 따라 행동을 조정.

물론 이건 고급 인공지능(딥러닝 등)이 아니라 **규칙 기반 AI**(Rule-based AI)에 속하지만, 게임 개발에서는 이런 단순한 알고리즘도 AI로 분류된다.
