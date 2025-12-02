# <span class="header-prerequisite">Prerequisite</span>
- [[Linear mapping]]
- [[Inner Product]]
- [[Eigen Value, Eigen Vector]]
- [[Normal Operator]]
- [[Spectral Theorem]]
- [[Orthogonal Matrix]]
- [[Unitary Matrix]]

# <span class="header-reference">Reference</span>
- Strang, Linear Algebra and Its Applications
- Trefethen & Bau, Numerical Linear Algebra
- Horn & Johnson, Matrix Analysis
- Golub & Van Loan, Matrix Computations

---

# <span class="header-definition">Definition</span>

**Singular Value Decomposition**^[특이값 분해] (SVD)는 **모든 행렬**을 세 개의 간단한 행렬의 곱으로 분해하는 방법이다.

## Matrix Form

$A \in \mathbb{R}^{m \times n}$ (또는 $\mathbb{C}^{m \times n}$)에 대해:

$$A = U \Sigma V^T$$

**Real case**:
- $U \in \mathbb{R}^{m \times m}$: orthogonal matrix^[직교 행렬] ($U^T U = I$)
- $\Sigma \in \mathbb{R}^{m \times n}$: diagonal matrix^[대각 행렬] (non-negative entries)
- $V \in \mathbb{R}^{n \times n}$: orthogonal matrix ($V^T V = I$)

**Complex case**:

$$A = U \Sigma V^*$$

- $U \in \mathbb{C}^{m \times m}$: unitary matrix^[유니터리 행렬] ($U^* U = I$)
- $\Sigma \in \mathbb{R}^{m \times n}$: diagonal matrix (실수 non-negative entries)
- $V \in \mathbb{C}^{n \times n}$: unitary matrix ($V^* V = I$)

## Singular Values

$\Sigma$의 대각 성분:

$$\Sigma = \begin{pmatrix} \sigma_1 & & & & \\ & \ddots & & & \\ & & \sigma_r & & \\ & & & 0 & \\ & & & & \ddots \end{pmatrix}$$

**관례**: $\sigma_1 \geq \sigma_2 \geq \cdots \geq \sigma_r > 0$

여기서:
- $\sigma_i$ = **singular values**^[특이값]
- $r = \text{rank}(A)$
- $\sigma_{r+1} = \cdots = \sigma_{\min(m,n)} = 0$

## Singular Vectors

**Left singular vectors**^[왼쪽 특이벡터]: $U$의 열벡터 $\mathbf{u}_1, \ldots, \mathbf{u}_m$

**Right singular vectors**^[오른쪽 특이벡터]: $V$의 열벡터 $\mathbf{v}_1, \ldots, \mathbf{v}_n$

**관계식**:

$$A \mathbf{v}_i = \sigma_i \mathbf{u}_i \quad \text{for } i = 1, \ldots, r$$

$$A \mathbf{v}_i = 0 \quad \text{for } i > r$$

---

# <span class="header-theorem">Existence and Uniqueness</span>

## Existence Theorem

**정리**: 모든 행렬 $A \in \mathbb{R}^{m \times n}$은 SVD를 가진다.

**증명 sketch**:

### Step 1: $A^T A$는 Symmetric Positive Semidefinite

$$A^T A \in \mathbb{R}^{n \times n}$$

**Symmetric**: $(A^T A)^T = A^T A$ 
**Positive semidefinite**: 

$$\mathbf{x}^T (A^T A) \mathbf{x} = \|A\mathbf{x}\|^2 \geq 0$$ 
### Step 2: Spectral Theorem for $A^T A$

$A^T A$ symmetric $\Rightarrow$ orthogonal diagonalization:

$$A^T A = V \Lambda V^T$$

where:
- $V$ orthogonal
- $\Lambda = \text{diag}(\lambda_1, \ldots, \lambda_n)$ with $\lambda_i \geq 0$

자세한 내용은 [[Spectral Theorem]] 참조

### Step 3: Define Singular Values

$$\sigma_i = \sqrt{\lambda_i}$$

**정의**: $\Sigma$를 $\sigma_i$를 대각 성분으로 하는 $m \times n$ 행렬

### Step 4: Construct $U$

**For $i = 1, \ldots, r$ (where $\sigma_i > 0$)**:

$$\mathbf{u}_i = \frac{1}{\sigma_i} A \mathbf{v}_i$$

**Verification (orthonormal)**:

$$\langle \mathbf{u}_i, \mathbf{u}_j \rangle = \frac{1}{\sigma_i \sigma_j} \langle A\mathbf{v}_i, A\mathbf{v}_j \rangle$$

$$= \frac{1}{\sigma_i \sigma_j} \mathbf{v}_i^T A^T A \mathbf{v}_j$$

$$= \frac{1}{\sigma_i \sigma_j} \mathbf{v}_i^T (\sigma_j^2 \mathbf{v}_j)$$

$$= \frac{\sigma_j}{\sigma_i} \delta_{ij}$$

따라서 $\langle \mathbf{u}_i, \mathbf{u}_j \rangle = \delta_{ij}$ 
**For $i = r+1, \ldots, m$**: Extend to orthonormal basis (Gram-Schmidt)

### Step 5: Verify $A = U \Sigma V^T$

$$A \mathbf{v}_i = \sigma_i \mathbf{u}_i \text{ for } i \leq r$$

$$A V = U \Sigma$$

$$A = U \Sigma V^T$$ 
## Uniqueness

**Singular values**: Unique (up to ordering)

**Singular vectors**: 
- Unique if all $\sigma_i$ distinct
- **Not unique** if $\sigma_i = \sigma_j$ for $i \neq j$ (degenerate case)

**자유도**: Subspace spanned by degenerate singular vectors is unique, but basis choice is not

---

# <span class="header-properties">Properties</span>

## Basic Properties

### 1. Rank

$$\text{rank}(A) = \text{number of nonzero singular values}$$

### 2. Four Fundamental Subspaces

**Column space**^[열공간]:

$$\text{Col}(A) = \text{span}\{\mathbf{u}_1, \ldots, \mathbf{u}_r\}$$

**Row space**^[행공간]:

$$\text{Row}(A) = \text{span}\{\mathbf{v}_1, \ldots, \mathbf{v}_r\}$$

**Null space**^[영공간]:

$$\text{Null}(A) = \text{span}\{\mathbf{v}_{r+1}, \ldots, \mathbf{v}_n\}$$

**Left null space**^[왼쪽 영공간]:

$$\text{Null}(A^T) = \text{span}\{\mathbf{u}_{r+1}, \ldots, \mathbf{u}_m\}$$

**Fundamental Theorem of Linear Algebra**:

$$\mathbb{R}^n = \text{Row}(A) \oplus \text{Null}(A)$$

$$\mathbb{R}^m = \text{Col}(A) \oplus \text{Null}(A^T)$$

### 3. Norms

**Operator norm**^[작용소 노름] (또는 spectral norm^[스펙트럼 노름]):

$$\|A\|_2 = \sigma_1 = \sigma_{\max}$$

**Frobenius norm**^[프로베니우스 노름]:

$$\|A\|_F = \sqrt{\sum_{i,j} a_{ij}^2} = \sqrt{\sum_{i=1}^{r} \sigma_i^2}$$

**Nuclear norm**^[핵 노름] (또는 trace norm^[대각합 노름]):

$$\|A\|_* = \sum_{i=1}^{r} \sigma_i$$

### 4. Matrix Relationships

$$A^T A = V \Sigma^T \Sigma V^T$$

$$A A^T = U \Sigma \Sigma^T U^T$$

**Eigenvalues**:
- $A^T A$의 eigenvalues = $\sigma_i^2$
- $A A^T$의 eigenvalues = $\sigma_i^2$

## Outer Product Form

$$A = \sum_{i=1}^{r} \sigma_i \mathbf{u}_i \mathbf{v}_i^T$$

**의미**: $A$를 rank-1 행렬들의 합으로 표현

**각 항**: $\sigma_i \mathbf{u}_i \mathbf{v}_i^T$ = rank-1 행렬

## Reduced SVD

**Full SVD**: $U \in \mathbb{R}^{m \times m}$, $\Sigma \in \mathbb{R}^{m \times n}$, $V \in \mathbb{R}^{n \times n}$

**Reduced SVD** (또는 **Thin SVD**):

$$A = \hat{U} \hat{\Sigma} \hat{V}^T$$

where:
- $\hat{U} \in \mathbb{R}^{m \times r}$: 처음 $r$개 열
- $\hat{\Sigma} \in \mathbb{R}^{r \times r}$: 대각 부분만
- $\hat{V} \in \mathbb{R}^{n \times r}$: 처음 $r$개 열

**장점**: 메모리 효율적, 계산 효율적

## Truncated SVD

**$k$-truncated SVD** ($k < r$):

$$A_k = \sum_{i=1}^{k} \sigma_i \mathbf{u}_i \mathbf{v}_i^T$$

**의미**: $A$의 rank-$k$ 근사

---

# <span class="header-theorem">Optimality Theorems</span>

## Eckart-Young Theorem

**정리** (**Best Low-Rank Approximation**):

$$A_k = \arg\min_{\text{rank}(B) \leq k} \|A - B\|_2$$

$$A_k = \arg\min_{\text{rank}(B) \leq k} \|A - B\|_F$$

**증명 (Frobenius norm case)**:

$$\|A - B\|_F^2 = \sum_{i,j} (a_{ij} - b_{ij})^2$$

$B$가 rank $k$이면, 적어도 $r - k$개의 singular values를 버려야 함

Frobenius norm으로:

$$\|A - A_k\|_F^2 = \sum_{i=k+1}^{r} \sigma_i^2$$

이것이 최소값! 
**의미**: Truncated SVD = **최적 low-rank 근사**

## Approximation Error

**Operator norm**:

$$\|A - A_k\|_2 = \sigma_{k+1}$$

**Frobenius norm**:

$$\|A - A_k\|_F = \sqrt{\sum_{i=k+1}^{r} \sigma_i^2}$$

**해석**: Singular values의 decay rate가 근사 정확도를 결정

---

# <span class="header-definition">Geometric Interpretation</span>

## Linear Transformation View

$$A: \mathbb{R}^n \to \mathbb{R}^m$$

**SVD 분해**: $A = U \Sigma V^T$

### Three Steps

1. **$V^T$**: Rotate in $\mathbb{R}^n$ (orthogonal basis change)
2. **$\Sigma$**: Scale and change dimension
3. **$U$**: Rotate in $\mathbb{R}^m$ (orthogonal basis change)

**시각화**:

```
Input space (ℝⁿ) → [Vᵀ] → Rotated → [Σ] → Scaled/Stretched → [U] → Output space (ℝᵐ)
```

## Unit Sphere Mapping

Unit sphere in $\mathbb{R}^n$:

$$S^{n-1} = \{\mathbf{x} : \|\mathbf{x}\| = 1\}$$

**Image under $A$**:

$$A(S^{n-1}) = \{\sigma_i \mathbf{u}_i : i = 1, \ldots, r\}$$

= **Ellipsoid** in $\mathbb{R}^m$

**Principal axes**: $\mathbf{u}_i$ (directions)

**Semi-axes lengths**: $\sigma_i$ (magnitudes)

## Principal Directions

**Maximum stretch**:

$$\max_{\|\mathbf{x}\|=1} \|A\mathbf{x}\| = \sigma_1$$

achieved at $\mathbf{x} = \mathbf{v}_1$

**Minimum stretch** (among non-null directions):

$$\min_{\|\mathbf{x}\|=1, \mathbf{x} \in \text{Row}(A)} \|A\mathbf{x}\| = \sigma_r$$

achieved at $\mathbf{x} = \mathbf{v}_r$

**직관**: SVD는 선형 변환의 "주축"과 "신장 정도"를 찾는다

---

# <span class="header-examples">Examples</span>

## Example 1: $2 \times 2$ Matrix

$$A = \begin{pmatrix} 4 & 0 \\ 3 & -5 \end{pmatrix}$$

### Step 1: Compute $A^T A$

$$A^T A = \begin{pmatrix} 4 & 3 \\ 0 & -5 \end{pmatrix} \begin{pmatrix} 4 & 0 \\ 3 & -5 \end{pmatrix} = \begin{pmatrix} 25 & -15 \\ -15 & 25 \end{pmatrix}$$

### Step 2: Eigenvalues of $A^T A$

$$\det(A^T A - \lambda I) = (25-\lambda)^2 - 225 = 0$$

$$\lambda_1 = 40, \quad \lambda_2 = 10$$

### Step 3: Singular Values

$$\sigma_1 = \sqrt{40} = 2\sqrt{10}, \quad \sigma_2 = \sqrt{10}$$

### Step 4: Right Singular Vectors

**For $\lambda_1 = 40$**:

$$\mathbf{v}_1 = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\ -1 \end{pmatrix}$$

**For $\lambda_2 = 10$**:

$$\mathbf{v}_2 = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\ 1 \end{pmatrix}$$

### Step 5: Left Singular Vectors

$$\mathbf{u}_1 = \frac{1}{\sigma_1} A \mathbf{v}_1 = \frac{1}{2\sqrt{10}} \begin{pmatrix} 4 \\ 8 \end{pmatrix} = \frac{1}{\sqrt{5}} \begin{pmatrix} 1 \\ 2 \end{pmatrix}$$

$$\mathbf{u}_2 = \frac{1}{\sigma_2} A \mathbf{v}_2 = \frac{1}{\sqrt{10}} \begin{pmatrix} 4 \\ -2 \end{pmatrix} = \frac{1}{\sqrt{5}} \begin{pmatrix} 2 \\ -1 \end{pmatrix}$$

### SVD

$$A = U \Sigma V^T$$

$$U = \frac{1}{\sqrt{5}} \begin{pmatrix} 1 & 2 \\ 2 & -1 \end{pmatrix}, \quad \Sigma = \begin{pmatrix} 2\sqrt{10} & 0 \\ 0 & \sqrt{10} \end{pmatrix}, \quad V = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 & 1 \\ -1 & 1 \end{pmatrix}$$

## Example 2: Rank-Deficient Matrix

$$A = \begin{pmatrix} 1 & 2 \\ 2 & 4 \end{pmatrix}$$

**Observation**: $\text{rank}(A) = 1$

$$A^T A = \begin{pmatrix} 5 & 10 \\ 10 & 20 \end{pmatrix}$$

**Eigenvalues**: $\lambda_1 = 25$, $\lambda_2 = 0$

**Singular values**: $\sigma_1 = 5$, $\sigma_2 = 0$

$$A = 5 \mathbf{u}_1 \mathbf{v}_1^T$$

**Only one term** in outer product expansion!

## Example 3: Diagonal Matrix

$$D = \begin{pmatrix} 3 & 0 & 0 \\ 0 & -2 & 0 \\ 0 & 0 & 1 \end{pmatrix}$$

**Already in SVD form** (up to sign adjustments):

$$\Sigma = \begin{pmatrix} 3 & 0 & 0 \\ 0 & 2 & 0 \\ 0 & 0 & 1 \end{pmatrix}$$

$$U = \begin{pmatrix} 1 & 0 & 0 \\ 0 & -1 & 0 \\ 0 & 0 & 1 \end{pmatrix}, \quad V = I$$

**Note**: Singular values는 항상 non-negative!

## Example 4: Rectangular Matrix

$$A = \begin{pmatrix} 1 & 2 \\ 3 & 4 \\ 5 & 6 \end{pmatrix} \in \mathbb{R}^{3 \times 2}$$

**Full SVD**: $U \in \mathbb{R}^{3 \times 3}$, $\Sigma \in \mathbb{R}^{3 \times 2}$, $V \in \mathbb{R}^{2 \times 2}$

**Reduced SVD**: $\hat{U} \in \mathbb{R}^{3 \times 2}$, $\hat{\Sigma} \in \mathbb{R}^{2 \times 2}$, $\hat{V} \in \mathbb{R}^{2 \times 2}$

**Computation**:

$$A^T A = \begin{pmatrix} 35 & 44 \\ 44 & 56 \end{pmatrix}$$

$$\lambda_1 \approx 90.4, \quad \lambda_2 \approx 0.6$$

$$\sigma_1 \approx 9.5, \quad \sigma_2 \approx 0.77$$

---

# <span class="header-examples">Applications</span>

## 1. Moore-Penrose Pseudoinverse

**Pseudoinverse**^[유사역행렬] (또는 **Moore-Penrose inverse**):

$$A^+ = V \Sigma^+ U^T$$

where $\Sigma^+$는 $\Sigma$의 pseudoinverse:

$$\Sigma^+ = \begin{pmatrix} \frac{1}{\sigma_1} & & & \\ & \ddots & & \\ & & \frac{1}{\sigma_r} & \\ & & & 0 \\ & & & & \ddots \end{pmatrix}$$

**Properties**:
- $A A^+ A = A$
- $A^+ A A^+ = A^+$
- $(A A^+)^T = A A^+$ (symmetric)
- $(A^+ A)^T = A^+ A$ (symmetric)

**응용**: Least squares solutions

$$\min_{\mathbf{x}} \|A\mathbf{x} - \mathbf{b}\|$$

**Solution**: $\mathbf{x} = A^+ \mathbf{b}$

## 2. Low-Rank Approximation

**문제**: 큰 행렬 $A$를 rank $k$ 행렬로 근사

**해결**: Truncated SVD

$$A_k = \sum_{i=1}^{k} \sigma_i \mathbf{u}_i \mathbf{v}_i^T$$

**Compression ratio**:

$$\frac{\text{원본 크기}}{\text{압축 크기}} = \frac{mn}{k(m+n+1)}$$

**예**: $1000 \times 1000$ 행렬, $k=10$

$$\frac{1000^2}{10(1000+1000+1)} \approx 50$$

50배 압축!

## 3. Principal Component Analysis (PCA)

**데이터 행렬**: $X \in \mathbb{R}^{n \times p}$ ($n$ samples, $p$ features)

**Center data**: $\tilde{X} = X - \bar{X}$

**SVD**: $\tilde{X} = U \Sigma V^T$

**Principal components**: $V$의 열벡터

**Scores**: $U \Sigma$ (transformed data)

**Variance explained**:

$$\frac{\sigma_i^2}{\sum_j \sigma_j^2}$$

**Dimensionality reduction**: Keep top $k$ components

$$\tilde{X}_k = U_k \Sigma_k V_k^T$$

## 4. Image Compression

**Gray-scale image**: $A \in \mathbb{R}^{m \times n}$ (pixel values)

**SVD**: $A = U \Sigma V^T$

**Compressed image**: $A_k = \sum_{i=1}^{k} \sigma_i \mathbf{u}_i \mathbf{v}_i^T$

**Storage**:
- Original: $mn$ values
- Compressed: $k(m+n+1)$ values

**Quality**: Depends on $k$ and singular value decay

## 5. Recommender Systems

**Rating matrix**: $R \in \mathbb{R}^{m \times n}$ (users $\times$ items)

**Problem**: Many missing entries (sparse)

**Matrix completion**: 

$$\min_X \|R_{\text{observed}} - X_{\text{observed}}\|_F + \lambda \|X\|_*$$

Nuclear norm regularization encourages low-rank

**SVD-based approach**: Fill missing entries with low-rank approximation

## 6. Signal Processing

**Signal denoising**: Signal + noise

$$A = A_{\text{signal}} + A_{\text{noise}}$$

**SVD**: $A = \sum_{i=1}^{r} \sigma_i \mathbf{u}_i \mathbf{v}_i^T$

**Assumption**: Signal has low rank, noise is spread out

**Denoised signal**: Keep top $k$ singular values

$$A_{\text{clean}} \approx \sum_{i=1}^{k} \sigma_i \mathbf{u}_i \mathbf{v}_i^T$$

## 7. Total Least Squares

**Ordinary least squares**: $\min_{\mathbf{x}} \|A\mathbf{x} - \mathbf{b}\|$

Assumes errors only in $\mathbf{b}$

**Total least squares**: $\min_{\Delta A, \Delta \mathbf{b}} \|(\Delta A, \Delta \mathbf{b})\|_F$

subject to $(A + \Delta A)\mathbf{x} = \mathbf{b} + \Delta \mathbf{b}$

Allows errors in both $A$ and $\mathbf{b}$

**Solution via SVD**: Right singular vector corresponding to smallest singular value

## 8. Latent Semantic Analysis (LSA)

**Term-document matrix**: $A \in \mathbb{R}^{m \times n}$ ($m$ terms, $n$ documents)

**SVD**: $A = U \Sigma V^T$

**Latent topics**: Columns of $U_k$ and $V_k$

**Query**: Project query vector into latent space

**Similarity**: Cosine similarity in reduced space

---

# <span class="header-remark">Computational Aspects</span>

## Algorithms

### 1. Golub-Reinsch Algorithm

**Classical method**: QR iteration on bidiagonal form

**Steps**:
1. Reduce $A$ to bidiagonal form via Householder reflections
2. Apply QR iteration to bidiagonal matrix
3. Extract $U$, $\Sigma$, $V$

**Complexity**: $O(mn^2)$ for $m \geq n$

**Stability**: Numerically stable

### 2. Jacobi Method

**Approach**: Iterative orthogonal transformations

**Advantage**: Very accurate for small matrices

**Disadvantage**: Slower than Golub-Reinsch

### 3. Divide-and-Conquer

**Idea**: Split matrix recursively

**Advantage**: Fast for large matrices

**Complexity**: $O(mn^2)$ but with better constants

### 4. Randomized SVD

**For large, low-rank matrices**:

**Steps**:
1. Random projection to low-dimensional subspace
2. Compute SVD of smaller matrix
3. Lift back to original space

**Complexity**: $O(mnk)$ for rank-$k$ approximation

**Trade-off**: Speed vs. accuracy

## Software Implementations

**MATLAB**: `[U, S, V] = svd(A)`

**Python (NumPy)**: `U, S, V = np.linalg.svd(A)`

**Python (SciPy)**: `scipy.sparse.linalg.svds` (sparse)

**Julia**: `svd(A)`

**C/Fortran (LAPACK)**: `DGESVD`, `ZGESVD`

## Numerical Considerations

### Conditioning

SVD is **backward stable**: Computed SVD is exact SVD of nearby matrix

$$\text{fl}(A) = (U + \delta U)(\Sigma + \delta \Sigma)(V + \delta V)^T$$

where $\|\delta U\|, \|\delta V\|, \|\delta \Sigma\| = O(\epsilon_{\text{machine}})$

### Rank Determination

**Problem**: When is $\sigma_i$ "effectively zero"?

**Threshold**: $\sigma_i < \tau$ where $\tau = \epsilon_{\text{machine}} \cdot \sigma_1$

**Numerical rank**: Number of singular values $> \tau$

### Truncation Error

$$\|A - A_k\|_2 = \sigma_{k+1}$$

**Rule of thumb**: Keep singular values until:

$$\sum_{i=1}^{k} \sigma_i^2 \geq 0.9 \sum_{i=1}^{r} \sigma_i^2$$

(90% energy retained)

---

# <span class="header-remark">Remark</span>

## SVD vs Eigendecomposition

### Similarities

- Both diagonalize a matrix
- Both use orthogonal/unitary matrices
- Both reveal structure

### Differences

| Property | SVD | Eigendecomposition |
|----------|-----|-------------------|
| **Applicability** | Any matrix | Square matrices only |
| **Existence** | Always exists | May not exist |
| **Matrices** | $U, \Sigma, V$ | $P, \Lambda, P^{-1}$ |
| **Orthogonality** | $U, V$ always orthogonal | $P$ orthogonal only if normal |
| **Values** | $\sigma_i \geq 0$ | $\lambda_i \in \mathbb{C}$ |
| **Interpretation** | Geometric stretching | Eigenvectors/eigenvalues |

### When Both Apply

Square matrix $A$:

- **Eigendecomposition**: $A = P \Lambda P^{-1}$
- **SVD**: $A = U \Sigma V^T$

**Relationship**: If $A$ normal (e.g., symmetric), then:

$$|\lambda_i| = \sigma_i$$

## Connection to Spectral Theorem

**Spectral Theorem**: Normal operators have orthonormal eigenbasis

**SVD**: All matrices have orthonormal singular bases

**SVD uses Spectral Theorem**:

Apply spectral theorem to $A^T A$ and $A A^T$ (both symmetric!)

$$A^T A = V \Sigma^2 V^T$$

$$A A^T = U \Sigma^2 U^T$$

자세한 내용은 [[Spectral Theorem]] 참조

## Historical Notes

**Eugenio Beltrami** (1835-1900): First appeared in 1873

**Camille Jordan** (1838-1922): Generalization in 1874

**James Joseph Sylvester** (1814-1897): Matrix form in 1889

**Erhard Schmidt** (1876-1959): Integral equations (1907)

**Gene Golub** (1932-2007): Modern numerical algorithms (1960s)

**Name**: "Singular" = not related to eigenvalues, but to singular solutions of systems

## Why "Singular"?

**Historical reason**: From theory of singular integral equations

**Modern interpretation**: Values characterizing "singularity" of linear map

- Large $\sigma_i$: Strong stretching
- Small $\sigma_i$: Weak stretching  
- $\sigma_i = 0$: Null space (singularity)

## Extensions and Generalizations

### Higher-Order SVD

**Tucker decomposition**: Multi-dimensional arrays (tensors)

$$\mathcal{A} = \mathcal{G} \times_1 U_1 \times_2 U_2 \times_3 U_3$$

### Tensor Decompositions

**CP decomposition** (CANDECOMP/PARAFAC):

$$\mathcal{A} = \sum_{r=1}^{R} \mathbf{a}_r \circ \mathbf{b}_r \circ \mathbf{c}_r$$

### Generalized SVD

**For matrix pencils**: $(A, B)$

$$A = U \Sigma_A X^T, \quad B = V \Sigma_B X^T$$

### CUR Decomposition

**Approximation using actual columns and rows**:

$$A \approx CUR$$

- $C$: Selected columns of $A$
- $R$: Selected rows of $A$
- $U$: Small "core" matrix

**Advantage**: Interpretability (actual data columns/rows)

## Common Patterns

### Pattern 1: Dimensionality Reduction

**Problem**: High-dimensional data

**Solution**: Project onto top $k$ singular vectors

**Result**: Retain most information with fewer dimensions

### Pattern 2: Noise Reduction

**Problem**: Noisy data

**Solution**: Truncate small singular values

**Result**: Separate signal from noise

### Pattern 3: Matrix Approximation

**Problem**: Large matrix

**Solution**: Low-rank approximation via truncated SVD

**Result**: Compressed representation

## Limitations

### 1. Computational Cost

**Full SVD**: $O(mn^2)$ for $m \geq n$

**Issue**: Expensive for very large matrices

**Solution**: Randomized SVD, sparse methods

### 2. Interpretability

**Singular vectors**: Linear combinations of original features

**Issue**: May lack physical interpretation

**Solution**: CUR decomposition, constrained methods

### 3. Missing Data

**Standard SVD**: Requires complete matrix

**Issue**: Real data often has missing entries

**Solution**: Matrix completion methods

### 4. Non-Negativity

**SVD**: No non-negativity constraints

**Issue**: Some applications need non-negative factors

**Solution**: Non-negative Matrix Factorization (NMF)

## 관련 개념

- [[Spectral Theorem]]: Theoretical foundation
- [[Eigen Value, Eigen Vector]]: Related decomposition
- [[Normal Operator]]: When SVD = eigendecomposition
- [[Orthogonal Matrix]]: Structure of $U, V$
- [[Unitary Matrix]]: Complex version
- [[Symmetric Matrix]]: $A^T A$ and $A A^T$
- [[Inner Product]]: Orthogonality

