# 코드 품질 검토 Subagent 프롬프트 템플릿

코드 품질 검토 subagent를 디스패치할 때 이 템플릿을 사용하세요.

**목적:** 구현이 잘 만들어졌는지 검증 (깔끔함, 테스트, 유지보수성)

**스펙 준수 검토 통과 후에만 디스패치하세요.**

```
Task tool (superpowers:code-reviewer):
  Use template at requesting-code-review/code-reviewer.md

  WHAT_WAS_IMPLEMENTED: [구현자의 보고서에서 가져온 내용]
  PLAN_OR_REQUIREMENTS: [plan-file]의 작업 N
  BASE_SHA: [작업 이전 커밋]
  HEAD_SHA: [현재 커밋]
  DESCRIPTION: [작업 요약]
```

**표준 코드 품질 항목 외에도 검토자가 확인해야 할 사항:**
- 각 파일이 명확하게 정의된 인터페이스를 가진 하나의 명확한 책임을 갖는가?
- 단위들이 독립적으로 이해하고 테스트할 수 있도록 분해되어 있는가?
- 계획의 파일 구조를 따르고 있는가?
- 이 구현이 이미 큰 새 파일을 만들었거나 기존 파일을 크게 증가시켰는가? (기존 파일 크기는 문제 삼지 말 것 — 이 변경이 기여한 부분에 집중)

**코드 검토자 반환 내용:** Strengths, Issues (Critical/Important/Minor), Assessment
