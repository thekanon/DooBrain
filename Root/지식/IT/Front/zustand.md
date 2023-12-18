[[React]] 상태 관리를 위한 라이브러리이다.

[[redux]]와 차이가 있다면 조금 더 심플하다는 것이다.

[[reducer]]를 통해 상태를 변경하는 redux 특유의 패턴은 없다.
그러나 set 함수를 통해 비슷하게 사용할 수는 있다.


zustand에 대한 간단한 요약
1. **상태 업데이트 (Updating state)**
    
    - Zustand 스토어 내부의 상태를 변경하는 방법.
    - `set` 함수를 사용해 상태를 업데이트합니다.
2. **[[불변 상태(Immutable State)]]와 병합 (Immutable state and merging)**
    
    - Zustand는 불변성을 유지하면서 상태를 업데이트합니다. 새 상태 객체를 반환함으로써 기존 상태와 병합합니다.
3. **Flux 영감을 받은 실천 (Flux inspired practice)**
    
    - Flux 아키텍처에서 영감을 받은 Zustand의 사용 방법. 액션과 스토어 업데이트를 명확히 구분합니다.
4. **자동 생성 선택자 (Auto Generating Selectors)**
    
    - Zustand에서는 필요한 상태 부분만 선택하여 사용할 수 있는 선택자를 자동으로 생성합니다.
5. **스토어 액션 없는 실천 (Practice with no store actions)**
    
    - 액션을 별도로 정의하지 않고, 상태 업데이트를 직접 수행하는 방식입니다.
6. **TypeScript 가이드 (TypeScript Guide)**
    
    - Zustand를 TypeScript와 함께 사용하는 방법을 안내합니다. 타입 안정성을 제공합니다.
7. **테스팅 (Testing)**
    
    - Zustand 스토어와 상태를 테스트하는 방법을 설명합니다.
8. **React 이벤트 핸들러 외부에서 액션 호출 (Calling actions outside a React event handler in pre React 18)**
    
    - React 18 이전 버전에서 React 이벤트 핸들러 외부에서 Zustand 액션을 호출하는 방법을 다룹니다.
9. **Map과 Set 사용 (Map and Set Usage)**
    
    - Zustand에서 JavaScript의 `Map`과 `Set`과 같은 자료구조를 상태로 사용하는 방법을 설명합니다.
10. **상태를 URL과 연결 (Connect to state with URL)**
    
    - URL의 변경을 상태에 반영하거나, 상태 변경을 URL에 반영하는 방법을 다룹니다.
11. **상태 초기화 방법 (How to reset state)**
    
    - Zustand 스토어의 상태를 초기 상태로 재설정하는 방법을 설명합니다.
12. **프롭스로 상태 초기화 (Initialize state with props)**
    
    - React 컴포넌트의 프롭스를 사용하여 Zustand 스토어의 상태를 초기화하는 방법을 다룹니다.
13. **슬라이스 패턴 (Slices Pattern)**
    
    - 큰 상태 객체를 여러 작은 '슬라이스'로 나누어 관리하는 패턴을 설명합니다. 이는 관리의 복잡성을 줄입니다.
14. **useShallow를 사용한 불필요한 리렌더링 방지 (Prevent rerenders with useShallow)**
    
    - `useShallow` 훅을 사용하여 컴포넌트의 불필요한 리렌더링을 방지하는 방법을 다룹니다. 상태의 특정 부분만 변경되었을 때 리렌더링을 최적화합니다.