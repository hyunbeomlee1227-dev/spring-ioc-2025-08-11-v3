<h1>🚀 스프링부트 IoC 컨테이너 클론 - v3</h1>

<div class="section">
    <h2>📌 핵심 개념</h2>
    <div class="box">
        Reflection + @Component 스캔을 활용하여 Bean을 자동 등록하고,
        생성자 기반 의존성 주입(DI)과 싱글톤 캐싱을 구현한 IoC 컨테이너
    </div>
</div>

<div class="section">
    <h2>1️⃣ 동작 흐름</h2>

<pre>
  <code>ApplicationContext 생성
        ↓
init() 실행 (@Component 스캔)
        ↓
beanDefinitionMap 등록
        ↓
genBean("beanName") 호출
        ↓
싱글톤 확인
        ↓
생성자 분석
        ↓
canResolve()로 의존성 가능 여부 체크
        ↓
getBeanByType()으로 의존성 재귀 생성
        ↓
객체 생성 (Reflection)
        ↓
singletonObjects 저장
  </code>
</pre>
</div>

<div class="section">
    <h2>2️⃣ 핵심 설계 포인트</h2>

<ul>
    <li>📌 이름 기반 Bean 조회 + 타입 기반 의존성 해결</li>
    <li>📌 생성자 기반 DI (Constructor Injection)</li>
    <li>📌 가장 많은 파라미터 생성자 선택 전략</li>
    <li>📌 재귀 호출 기반 의존성 해결</li>
    <li>📌 싱글톤 캐싱 구조</li>
</ul>
</div>

<div class="section">
    <h2>3️⃣ 핵심 특징</h2>

<ul>
    <li>@Component 기반 자동 Bean 등록</li>
    <li>Reflections 기반 패키지 스캔</li>
    <li>Reflection 기반 객체 생성</li>
    <li>타입 기반 DI 자동 해결</li>
    <li>canResolve()를 통한 생성 가능성 검증</li>
</ul>
</div>
<div class="section">
    <h2>4️⃣ 후기</h2>
<ul>
        <li>v1에서는 모든 Bean을 수동으로 생성했지만,
        v2에서는 <b>어노테이션 기반 스캔 + Reflection + DI 자동화</b>를 통해
        Spring의 핵심 구조를 모사하였습니다.</li>
        <li>이를 통해 Bean 등록 → 의존성 해결 → 싱글톤 관리라는
        Spring 컨테이너의 핵심 흐름을 직접 구현할 수 있었습니다.</li>
</ul>
        
</div>

