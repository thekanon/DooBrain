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
    - [[Flux]] 아키텍처에서 영감을 받은 Zustand의 사용 방법. 액션과 스토어 업데이트를 명확히 구분합니다.
    - 단일 [[스토어(Store)]]가 좋지만 여러 조각으로 store를 분할 할 수 있음.
    - [[reducer]]를 사용하지 않아도 되지만 굳이 사용해야 한다면 store의 루트레벨에서 [[디스패치(dispatch)]]를 정의할 수 있음.
    - [[미들웨어(middleware)]]를 통해 비동기처리, 상태 지속 등에 활용할 수 있음
4. **자동 생성 선택자 (Auto Generating Selectors)**
    - Zustand 스토어에서 필요한 부분의 상태만 선택적으로 구독할 수 있도록 도와줍니다. 이를 통해 컴포넌트가 스토어의 특정 부분에만 의존하게 되며, 상태의 다른 부분이 변경되어도 해당 컴포넌트가 불필요하게 리렌더링 되는 것을 방지할 수 있습니다.
    - 복잡하고 어려운 방식으로 redux와 유사한 함수를 직접 정의할 수도 있습니다.
5. **스토어 액션 없는 실천 (Practice with no store actions)**
    - 액션을 별도로 정의하지 않고, 상태 업데이트를 직접 수행하는 방식입니다.
6. **TypeScript 가이드 (TypeScript Guide)**
    - TypeScript를 사용할 때의 차이점은 `create(...)`을 작성하는 대신 `create<T>()(...)`를 작성해야 한다는 것입니다(추가 괄호에 주의하세요 `()` 또한 유형 매개변수와 함께) 여기서 `T`는 주석을 추가할 상태의 유형입니다.
    - 왜 초기상태에서 유형 추론이 안되냐면, T는 불변이기 때문임.
7. **테스팅 (Testing)**
    - #### 당장 필요없는 것 같아서 나중에 읽음`
8. **React 이벤트 핸들러 외부에서 액션 호출 (Calling actions outside a React event handler in pre React 18)**
    - React는 이벤트 핸들러 외부에서 호출되는 경우 setState를 동기적으로 처리하기 때문에 이벤트 핸들러 외부에서 state를 업데이트하면 React가 컴포넌트를 동기적으로 업데이트하게 됩니다. 따라서 좀비 자식 효과가 발생할 위험이 있습니다. 이벤트 핸들러 외부에서 호출될때는 unstable_batchedUpdates를 사용해야 합니다.
9. **Map과 Set 사용 (Map and Set Usage)**
    - Zustand에서 JavaScript의 `Map`과 `Set`과 같은 자료구조를 상태로 사용할 수 있습니다.
10. **상태를 URL과 연결 (Connect to state with URL)**
    - [[store]]의 상태를 URL 해시에 연결하려면 자체 해시 저장소를 생성할 수 있습니다.
    - URL 쿼리 매개변수를 state에 연결할 수 있습니다.
11. **상태 초기화 방법 (How to reset state)**
    1. initialState 객체로 한번에 변경
    2. 별도의 액션을 정의하여 초기화
    3. persist 등 별도의 라이브러리 사용
12. **프롭스로 상태 초기화 (Initialize state with props)**
    
    - React 컴포넌트의 프롭스를 사용하여 Zustand 스토어의 상태를 초기화하는 방법을 다룹니다.
13. **슬라이스 패턴 (Slices Pattern)**
    
    - 큰 상태 객체를 여러 작은 '슬라이스'로 나누어 관리하는 패턴을 설명합니다. 이는 관리의 복잡성을 줄입니다.
14. **useShallow를 사용한 불필요한 리렌더링 방지 (Prevent rerenders with useShallow)**
    
    - `useShallow` 훅을 사용하여 컴포넌트의 불필요한 리렌더링을 방지하는 방법을 다룹니다. 상태의 특정 부분만 변경되었을 때 리렌더링을 최적화합니다.