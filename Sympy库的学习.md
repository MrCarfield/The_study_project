Sympy库的学习

### 1. **符号变量定义**

- `symbols()`：定义符号变量---将字符串字母变成真正的python变量

  ```python
  from sympy import symbols
  x, y = symbols('x y')
  ```

### 2. **表达式创建与化简**

- `sympify()`：将字符串转化为 `SymPy` 表达式---变成计算机所认识的表达式,其中字符串中的|代表析取, &代表合取, ~代表非, >>代表单条件, ==代表等值

  ```python
  from sympy import sympify
  expr = sympify('x**2 + 2*x + 1')
  ```

- `simplify()`：简化表达式。

  ```python
  from sympy import simplify
  expr=sympify("(x**2 - 1)/(x - 1)")
  print(simplify(expr))
  ```

### 3. **代数运算**

- `expand()`：展开多项式。

  ```python
  from sympy import expand
  expand((x + 1)*(x + 2))
  ```

- `factor()`：因式分解。

  ```python
  from sympy import factor
  factor(x**2 - 1)
  ```

- `collect()`：收集类似项。

  ```python
  from sympy import collect
  expr=sympify("x**2 + 2*x + 3*x")
  x=sympify("x")
  print(collect(expr, x))
  ```

### 4. **方程求解**

- `solve()`：解代数方程。

  ```python
  from sympy import *
  x=sympify("x")
  solve(x**2 - 4, x)
  ```

- `Eq()`：构造等式。

  ```python
  from sympy import Eq
  eq = Eq(x**2 - 4, 0)
  solve(eq, x)
  ```

### 5. **微积分**

- `diff()`：求导。

  ```python
  from sympy import diff
  diff(x**2 + 2*x + 1, x)
  ```

- `integrate()`：积分。

  ```python
  from sympy import integrate
  integrate(x**2, x)
  ```

- `limit()`：计算极限。

  ```python
  from sympy import limit
  limit(1/x, x, 0)
  ```

### 6. **矩阵运算**

- `Matrix()`：创建矩阵。

  ```python
  from sympy import Matrix
  A = Matrix([[1, 2], [3, 4]])
  ```

- `inv()`：计算矩阵的逆。

  ```python
  A.inv()
  ```

- `det()`：计算矩阵的行列式。

  ```python
  A.det()
  ```

### 7. **逻辑运算符**

- `And()`：逻辑与。

  ```python
  from sympy.logic.boolalg import And
  And(x > 1, y < 5)
  ```

- `Or()`：逻辑或。

  ```python
  from sympy.logic.boolalg import Or
  Or(x > 1, y < 5)
  ```

- `Not()`：逻辑非。

  ```python
  from sympy.logic.boolalg import Not
  Not(x > 1)
  ```

- `Equivalent()`：等价（双向蕴含）。

  ```python
  from sympy.logic.boolalg import Equivalent
  Equivalent(x > 1, y < 5)
  ```

- `Imply()`：蕴含。

  ```python
  from sympy.logic.boolalg import Imply
  Imply(x > 1, y < 5)
  ```

### 8. **符号求和与求积**

- `Sum()`：符号求和。

  ```python
  from sympy import Sum
  Sum(x, (x, 1, 10))  # 求和 x 从 1 到 10
  ```

- `Product()`：符号求积。

  ```python
  from sympy import Product
  Product(x, (x, 1, 10))  # 求积 x 从 1 到 10
  ```

### 9. **极限与级数**

- `series()`：泰勒级数展开。

  ```python
  from sympy import series
  series(exp(x), x, 0, 5)
  ```

- `limit()`：求极限。

  ```python
  from sympy import limit
  limit(sin(x)/x, x, 0)
  ```

### 10. **符号化简和变换**

- `subs()`：替换表达式中的符号。

  ```python
  expr = x**2 + 2*x + 1
  expr.subs(x, 3)
  ```

- `expand_trig()`：展开三角函数。

  ```python
  from sympy import expand_trig
  expand_trig(sin(x + y))
  ```

### 11. **求解不等式**

- `solve_univariate_inequality()`：求解一元不等式。

  ```python
  from sympy.solvers.inequalities import solve_univariate_inequality
  solve_univariate_inequality(x**2 - 4 < 0, x)
  ```

### 12. **数值计算**

- `evalf()`：将表达式转为数值（浮动点数）。

  ```python
  expr = sqrt(2)
  expr.evalf()
  ```

### 13. **常见常数和数学函数**

- `pi`：圆周率。

  ```python
  from sympy import pi
  pi
  ```

- `E`：自然对数的底数。

  ```python
  from sympy import E
  E
  ```

- `gamma`：欧拉常数。

  ```python
  from sympy import gamma
  gamma(5)
  ```

### 14. **解线性方程组**

- `linsolve()`：解线性方程组。

  ```python
  from sympy import linsolve, symbols
  x, y = symbols('x y')
  eq1 = Eq(x + y, 10)
  eq2 = Eq(x - y, 2)
  linsolve([eq1, eq2], x, y)
  ```

