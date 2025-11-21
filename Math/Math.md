# Mathematics Overview

Math 분야별 주제 및 핵심 개념 정리

---

## 🔢 Algebra

### Abstract Algebra
- **Group^[군]**, **Ring^[환]**, **Field^[체]**의 구조와 성질
- Homomorphism^[준동형사상], Isomorphism^[동형사상]
- Quotient structures^[몫 구조], Normal subgroups^[정규 부분군]

#### Representation Theory
- Group과 Ring을 linear transformation^[선형 변환]으로 표현
- Characters^[지표], Irreducible representations^[기약 표현]
- Schur's lemma, Maschke's theorem

### Linear Algebra
- [[Linear mapping]], Vector spaces^[벡터 공간], [[Dual Spaces]]
- [[Dual of a Linear Map]]: 쌍대 사상, 전치
- [[Double dual]]: 이중 쌍대, 자연 매장, 반사 공간
- Eigenvalues^[고유값], Eigenvectors^[고유벡터]
- Inner product spaces^[내적 공간], Orthogonality^[직교성]

---

## 📈 Analysis

### Real and Complex Analysis
- Limits^[극한], Continuity^[연속성], Differentiation^[미분]
- Integration theory^[적분 이론] (Riemann, Lebesgue)
- [[Measure Space]]: 측도 공간, 가측 함수, 르베스그 적분
- [[Subspace Measure]]: 추적 시그마 대수, 제한 측도, 조건부 확률
- [[Monotone Convergence Theorem]], [[Dominated Convergence Theorem]], [[Fatou's Lemma]]: 수렴 정리
- Complex functions^[복소함수], Holomorphic functions^[정칙함수]
- Cauchy's theorem, Residue calculus^[유수 계산]

### Functional Analysis
- [[Hilbert Space]], [[Riesz Representation Theorem]]
- Banach spaces^[바나흐 공간]
- Bounded operators^[유계 연산자], Spectral theory^[스펙트럼 이론]
- Weak topology^[약한 위상], Hahn-Banach theorem

### Fourier Analysis
- Fourier series^[푸리에 급수], Fourier transform^[푸리에 변환]
- Convolution^[합성곱], Plancherel theorem
- Harmonic analysis^[조화 해석]

### Partial Differential Equations
- Classification: Elliptic, Parabolic, Hyperbolic
- Boundary value problems^[경계값 문제]
- Sobolev spaces^[소볼레프 공간]
- Weak solutions^[약한 해], Distributions^[분포]

---

## 🔷 Topology

### Algebraic Topology
- Fundamental group^[기본군], Homotopy^[호모토피]
- Homology^[호몰로지], Cohomology^[코호몰로지]
- CW complexes, Simplicial complexes^[단체 복합체]

### Differential Topology
- Smooth manifolds^[매끄러운 다양체]
- [[Differential Forms]], [[Tensor]]
- Stokes' theorem, De Rham cohomology
- Vector bundles^[벡터 다발], Characteristic classes^[특성류]

---

## 📐 Geometry

### Differential Geometry
- Riemannian manifolds^[리만 다양체]
- Curvature^[곡률]: Gaussian, Ricci, Sectional
- Geodesics^[측지선], Parallel transport^[평행 이동]
- Gauss-Bonnet theorem

### Algebraic Geometry
- Varieties^[대수적 다양체], Schemes^[스킴]
- Sheaf theory^[층 이론]
- Coherent sheaves^[연접층]
- Intersection theory^[교차 이론]

---

## 🔢 Number Theory

### Algebraic Number Theory
- Algebraic integers^[대수적 정수], Number fields^[수체]
- Class groups^[류군], Ideal theory^[아이디얼 이론]
- Dedekind domains, Ramification^[분기]

### Analytic Number Theory
- Prime number theorem^[소수 정리]
- L-functions, Riemann zeta function
- Dirichlet series, Modular forms^[모듈러 형식]

### Arithmetic Geometry
- Elliptic curves^[타원 곡선]
- Diophantine equations^[디오판토스 방정식]
- Mordell-Weil theorem
- Rational points^[유리점]

### Computational Number Theory
- Primality testing^[소수 판정]
- Factorization algorithms^[인수분해 알고리즘]
- Cryptography^[암호학]

---

## 🎲 Probability Theory

### Foundations and core concepts^[기초 및 핵심 개념]
- [[Probability]]: 확률론의 개관, 해석, 역사
- [[Sample Spaces]]: 표본 공간, 사건, 확률 측도의 공리
- [[Borel Sigma Algebra]]: 측도론적 배경
- [[Random Variables]]: 확률 변수, 분포, CDF
- [[Probability Mass Function]]: 이산 확률 변수의 PMF
- [[Probability Density Function]]: 연속 확률 변수의 PDF
- [[Expected Value]]: 기댓값, 분산, 적률

### Conditional probability and inference^[조건부 확률과 추론]
- [[Joint Probabilities]]: 결합 확률, 결합 분포
- [[Marginal Probabilities]]: 주변 확률, 주변화
- [[Conditional Probability]]: 조건부 확률, 독립
- [[Law of Total Probability]]: 전확률 공식
- [[Bayes' Rule]]: 베이지안 추론
- [[Recursive Thinking]]: 재귀적 사고, 동적 계획법

### Stochastic Processes
- Random walks^[랜덤 워크], Markov chains^[마르코프 연쇄]
- Brownian motion^[브라운 운동]
- Martingales^[마틴게일]
- Poisson processes^[푸아송 과정]

### Probabilistic Models of Critical Phenomena
- Phase transitions^[상전이]
- Percolation theory^[침투 이론]
- Ising model
- Statistical mechanics^[통계역학]

### High-Dimensional Geometry and Its Probabilistic Analogues
- Concentration of measure^[측도의 집중]
- Random matrices^[랜덤 행렬]
- Isoperimetric inequalities^[등주 부등식]

---

## 🧮 Combinatorics

### Enumerative and Algebraic Combinatorics
- [[Permutations and Combinations]]: 순열, 조합, 이항 정리
- Counting techniques^[계수 기법]
- Generating functions^[생성함수]
- Partition theory^[분할 이론]
- Young tableaux

### Extremal and Probabilistic Combinatorics
- Ramsey theory^[램지 이론]
- Graph limits^[그래프 극한]
- Random graphs^[랜덤 그래프]
- Turán-type problems

---

## 🔄 Group Theory

### Geometric and Combinatorial Group Theory
- Free groups^[자유군], Presentations^[표현]
- Group actions on spaces^[공간에 대한 군의 작용]
- Cayley graphs^[케일리 그래프]
- Hyperbolic groups^[쌍곡 군]

---

## 🧩 Logic

### Set Theory
- Axioms (ZFC)
- Cardinals^[기수], Ordinals^[서수]
- Continuum hypothesis^[연속체 가설]
- Forcing^[강제법]

### Model Theory
- Structures^[구조], Languages^[언어]
- Completeness^[완전성], Compactness^[컴팩트성]
- Categoricity^[범주성]
- Types^[타입], Saturated models^[포화 모델]

---

---

# Applied Mathematics 🔧

## 🖥️ Computation

### Computational Science
- Numerical simulations^[수치 시뮬레이션]
- High-performance computing^[고성능 컴퓨팅]
- Scientific computing^[과학 계산]

### Numerical Methods
- Finite difference methods^[유한 차분법]
- Finite element methods^[유한 요소법]
- Spectral methods^[스펙트럼 방법]

#### Continuous Optimization^[연속 최적화]
- Gradient descent^[경사 하강법]
- Newton's method^[뉴턴 방법]
- Convex optimization^[볼록 최적화]
- Linear programming^[선형 계획법]

#### Numerical Solution of ODEs
- Euler method, Runge-Kutta methods
- Multistep methods^[다단계 방법]
- Stiff equations^[강성 방정식]

#### Numerical Solution of PDEs
- Finite element method (FEM)
- Finite volume method (FVM)
- Boundary element method (BEM)

### Numerical Linear Algebra and Matrix Analysis
- Matrix decompositions^[행렬 분해]: LU, QR, SVD
- Eigenvalue problems^[고유값 문제]
- Iterative methods^[반복법]: Krylov subspace
- Sparse matrices^[희소 행렬]

### Data Mining and Analysis
- Clustering^[군집화], Classification^[분류]
- Dimension reduction^[차원 축소]: PCA, t-SNE
- Machine learning algorithms^[기계 학습 알고리즘]

### Network Analysis
- Graph algorithms^[그래프 알고리즘]
- Community detection^[커뮤니티 탐지]
- Network centrality^[네트워크 중심성]

---

## ⚙️ Control Theory^[제어 이론]

- State-space models^[상태 공간 모델]
- Controllability^[제어 가능성], Observability^[관측 가능성]
- Optimal control^[최적 제어]
- Lyapunov stability^[리아푸노프 안정성]
- Feedback control^[피드백 제어]

---

## 📡 Signal Processing^[신호 처리]

- Digital signal processing (DSP)
- Filtering^[필터링]: Low-pass, High-pass, Band-pass
- Sampling theory^[표본화 이론]
- Wavelet transform^[웨이블릿 변환]
- Time-frequency analysis^[시간-주파수 해석]

---

## 📊 Information Theory^[정보 이론]

- Entropy^[엔트로피], Mutual information^[상호 정보량]
- Channel capacity^[채널 용량]
- Source coding^[소스 코딩], Channel coding^[채널 코딩]
- Error-correcting codes^[오류 정정 부호]
- Shannon's theorem

---

## 🔍 Inverse Problems^[역문제]

- Ill-posed problems^[부적절 문제]
- Regularization^[정칙화]: Tikhonov, Total variation
- Tomography^[단층촬영]: CT, MRI
- Parameter identification^[매개변수 식별]

---

## 🌊 Mathematical Physics^[수리 물리학]

### Classical Mechanics^[고전 역학]
- Lagrangian mechanics^[라그랑주 역학]
- Hamiltonian mechanics^[해밀턴 역학]
- Variational principles^[변분 원리]

### Continuum Mechanics^[연속체 역학]
- Elasticity theory^[탄성 이론]
- Plasticity^[소성]
- Stress-strain relations^[응력-변형 관계]

### Fluid Dynamics^[유체 역학]
- Navier-Stokes equations^[나비에-스토크스 방정식]
- Turbulence^[난류]
- Boundary layers^[경계층]

#### Magnetohydrodynamics (MHD)
- Plasma physics^[플라즈마 물리학]
- Magnetic fields in fluids
- Alfvén waves^[알벤 파동]

### Kinetic Theory^[운동론]
- Boltzmann equation^[볼츠만 방정식]
- Statistical mechanics^[통계역학]
- Phase space^[위상 공간]

### Quantum Mechanics^[양자역학]
- Schrödinger equation^[슈뢰딩거 방정식]
- Wave functions^[파동 함수]
- Operators and observables^[연산자와 관측량]
- Quantum entanglement^[양자 얽힘]

### General Relativity and Cosmology^[일반 상대성이론과 우주론]
- Einstein field equations^[아인슈타인 장 방정식]
- Black holes^[블랙홀]
- Gravitational waves^[중력파]
- Cosmological models^[우주론적 모델]

### Soft Matter^[소프트 물질]
- Polymers^[고분자], Colloids^[콜로이드]
- Liquid crystals^[액정]
- Granular materials^[입상 물질]

### Effective Medium Theories^[유효 매질 이론]
- Homogenization^[균질화]
- Composite materials^[복합 재료]

### Earth System Dynamics^[지구 시스템 역학]
- Climate modeling^[기후 모델링]
- Geophysical fluid dynamics^[지구물리 유체역학]
- Atmosphere-ocean coupling^[대기-해양 결합]

---

## 📈 Applied Combinatorics and Graph Theory

- Network optimization^[네트워크 최적화]
- Scheduling problems^[스케줄링 문제]
- Graph coloring^[그래프 색칠]
- Matching theory^[매칭 이론]
- Flow networks^[흐름 네트워크]

---

## 📊 Pure Math Fields

### [[Category Theory]]
- Categories^[범주], Functors^[함자], Natural transformations^[자연 변환]
- Universal properties^[보편 성질]
- Adjoint functors^[수반 함자]
- Limits and colimits^[극한과 여극한]

### Calculus
- Derivatives^[도함수], Integrals^[적분]
- Fundamental theorem of calculus^[미적분학의 기본정리]
- Multivariable calculus^[다변수 미적분]
- Vector calculus^[벡터 미적분]

### Dynamical Systems
- Fixed points^[고정점], Stability^[안정성]
- Bifurcations^[분기]
- Chaos theory^[카오스 이론]
- Ergodic theory^[에르고딕 이론]

### Applied Math / Numerical Analysis
- Numerical methods^[수치 방법]
- Finite element method^[유한 요소법]
- Optimization^[최적화]
- Error analysis^[오차 해석]

### Moduli Spaces
- Parameter spaces^[매개변수 공간]
- Moduli of curves^[곡선의 모듈라이]
- Deformation theory^[변형 이론]
- Geometric invariant theory^[기하적 불변량 이론]

---

## 📚 Cross-cutting Concepts

수학 전반에 걸쳐 나타나는 핵심 개념들:

- **Structure-preserving maps**: Homomorphisms, Continuous maps, Smooth maps
- **Equivalence relations**: Isomorphism, Homeomorphism, Diffeomorphism
- **Duality**: [[Dual Spaces]], Pontryagin duality, Langlands duality
- **Symmetry**: Group actions, Representation theory
- **Topology vs Geometry**: Continuous vs Smooth structures
- **Discrete vs Continuous**: Combinatorics vs Analysis
- **Local vs Global**: Local properties vs Global invariants

---

## 노트 링크

현재 작성된 노트:
- [[Linear mapping]]
- [[Dual Spaces]]
- [[Hilbert Space]]
- [[Tensor]]
- [[Differential Forms]]
- [[Riesz Representation Theorem]]
- [[Category Theory]]
- [[Borel Sigma Algebra]]
- [[Sample Spaces]]
- [[Conditional Probability]]
- [[Bayes' Rule]]

