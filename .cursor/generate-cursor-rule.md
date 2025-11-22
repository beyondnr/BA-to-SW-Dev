# 커서 룰(Cursor Rule) 생성 가이드라인

새로운 커서 룰(`.mdc` 파일)을 생성할 때, 일관성과 효율성을 위해 다음 가이드라인을 따르십시오.

## 1. 파일 명명 및 위치 (File Naming and Location)
- **확장자 (Extension)**: 룰 파일은 항상 `.mdc` 확장자를 사용합니다.
- **위치 (Location)**: 파일은 `.cursor/rules/` 디렉터리에 위치해야 합니다.
- **명명 규칙 (Naming)**: 파일명은 `kebab-case`(소문자 및 하이픈)를 사용합니다 (예: `react-components.mdc`, `python-formatting.mdc`).

## 2. 메타데이터 (Frontmatter)
모든 룰 파일은 파일 최상단에 다음 내용을 포함하는 YAML frontmatter 블록으로 시작해야 합니다:
- `description`: 이 룰이 무엇을 강제하거나 돕는지에 대한 간결한 요약 설명입니다.
- `globs`: 이 룰이 적용될 파일 패턴(glob 패턴)의 목록입니다. 불필요한 노이즈를 줄이기 위해 구체적으로 지정하는 것이 좋습니다.

## 3. 내용 구조 (Content Structure)
룰의 본문은 명확하고 실행 가능해야 합니다. 다음 섹션들을 활용하여 구성하십시오:
- **Context (문맥)**: 이 룰이 언제 적용되는지 설명합니다. (예: "React 컴포넌트를 작성할 때...", "테스트 코드를 작성할 때...")
- **Rules (규칙)**: 따라야 할 구체적인 지침, 제약 사항, 또는 모범 사례를 나열합니다.
- **Examples (예시)**: 룰을 명확히 이해할 수 있도록 '좋은 예(Good Example)'와 '나쁜 예(Bad Example)'를 포함합니다.

## 4. 템플릿 (Template)

새로운 룰을 만들 때 아래 템플릿을 복사하여 사용하십시오:

```markdown
---
description: [룰에 대한 짧은 설명]
globs: [ "*.ts", "*.tsx", "src/components/**" ]
---

# [룰 이름]

## Context
[이 룰이 적용되는 상황을 설명합니다. 예: "React 함수형 컴포넌트를 생성하거나 수정할 때 적용합니다."]

## Requirements
- [요구사항 1]
- [요구사항 2]
- [요구사항 3]

## Examples

<example>
// Good Example
export const MyComponent = () => {
  return <div>Hello</div>;
};
</example>

<example>
// Bad Example
export function myComponent() {
  return <div>Hello</div>;
}
</example>
```
