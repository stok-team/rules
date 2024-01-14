# Typing
파이썬 타입과 관련된 규칙을 정의합니다.

## 환경

- 실시간 타입 검사 및 추론을 위해 Visual Studio Code를 사용합니다.
  - `settings.json`에서 다음 설정을 사용합니다.
  - ```json
    "python.languageServer": "Pylance",
    "python.analysis.typeCheckingMode": "strict",
    ```
- 타입 검사기로 `pyright`를 채택합니다.

## 규칙

### `typing.Any` 사용 지양
- 부득이하게 `typing.Any`를 사용하는 경우에는 반드시 합리적인 이유가 필요합니다.
- Top type의 목적으로 `typing.Any`를 사용해서는 안 됩니다. Top type으로는 `object`를 사용합니다.

### PEP 695: Python 3.12 이상 인터프리터를 사용하는 경우 PEP 695를 적용합니다.
- `typing.TypeAlias`를 사용하지 않습니다. 이것 대신 type statement를 사용합니다.
- `TypeVar` 사용을 지양합니다. 이것 대신 type parameter syntax를 사용합니다. 꼭 필요한 경우 근거를 제시할 수 있어야 합니다.

### Nested Generics
- 중첩된 제네릭은 최대한 상세하게 적되, 너무 복잡해지지 않는 깊이를 작성자와 리뷰어가 판단합니다.
- 복잡하지만 구체적으로 표현할 필요가 있는 경우 여러 단계로 나누어 작성하는 것을 검토합니다.

### 함수
- 함수의 인자 타입과 리턴 타입은 항상 적습니다.
