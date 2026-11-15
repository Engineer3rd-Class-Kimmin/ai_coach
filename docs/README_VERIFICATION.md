# 공개 코드 검증 기록

2026-11-15 · Python 3.11.9 · Windows · ai-assisted

명령(저장소 루트, ai_coach의 PYTHONPATH는 PowerShell에서 `$env:PYTHONPATH`로 설정):

```text
PYTHONPATH=apps/api/src python -m pytest -q apps/api/tests/test_coaching_interpretation.py
```

실제 관측: **10 passed, 8 subtests passed**.

Mock 모델을 사용한 근거·해석·출력 계약. 실제 Qwen·검색·사용자 효과 평가가 아니다.

테스트 입력은 해당 테스트 파일에 고정되어 있다. 기대값은 변경하지 않았다.

| 검토한 코드·입력 | SHA-256 |
|---|---|
| `apps/api/tests/test_coaching_interpretation.py` | `a12ee99c2ce7fd66ffb31fe6227c0273102be7f0a92d424d57858b5be47e89ec` |
| `apps/api/src/coach_dialogue.py` | `8aeb998bebe4514f53b117c69a0d01d276ef419ceb9736176111a126fee1e90d` |
| `apps/api/src/coaching_interpretation.py` | `401a70d0641970b3945d46a4773c0000b678d6341064ae26fdba5852bd03cdd9` |

전체 `apps/api/tests` 실행도 시도했으나 이 환경의 55초 제한에서 완료하지 못했다. 전체 통과나 실서버 재평가로 표시하지 않는다. 전체 평가의 자산 조건은 [평가 실행 안내](../evaluation/README.md)를 따른다.
