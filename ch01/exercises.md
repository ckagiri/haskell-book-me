# Exercises

## Chapter Exercises

### Combinators
Determine if each of the following are combinators or not.
1. `λx.xxx`

   **Yes**. The body only contains *𝑥*, which is also in the head.

2. `λxy.zx`

    **No**. *𝑧* is a free variable.

3. `λxyz.xy(zx)`

    **Yes**. All three variables contained in the body are also in the head.

4. `λxyz.xy(zxy)`

    **Yes**. All three variables contained in the body are also in the head.

5. `λxy.xy(zxy)`

    **No**. *𝑧* is a free variable.

### Normal form or diverge?
Determine if each of the following can be reduced to a normal form or if they diverge.
1. `λx.xxx`

    already in **normal form**

2. `(λz.zz)(λy.yy)`

    **Diverges**, it is the *omega* term (alpha-equivalent to *(𝜆𝑥.𝑥𝑥)(𝜆𝑥.𝑥𝑥)*)

3. `(λx.xxx)z`

    **Can be reduced** to *𝑧𝑧𝑧*.

### Beta reduce
Evaluate (that is, beta reduce) each of the following expressions to normal form.
1. `(λabc.cba)zz(λwv.w)`

   (λabc.cba)zz(λwv.w)  
   (λbc.cbz)z(λwv.w)  
   (λc.czz)(λwv.w)  
   (λwv.w)zz  
   (λv.z)z  
   **z**

2. `(λx.λy.xyy)(λa.a)b`

   (λx.λy.xyy)(λa.a)b  
   (λy.(λa.a)yy)b  
   (λa.a)bb  
   **bb**

3. `(λy.y)(λx.xx)(λz.zq)`

   (λy.y)(λx.xx)(λz.zq)  
   (λx.xx)(λz.zq)  
   (λz.zq)(λz.zq)  
   (λz.zq)q  
   **qq**

4. `(λz.z)(λz.zz)(λz.zy)`

   (λz.z)(λz.zz)(λz.zy)  
   (λz.zz)(λz.zy)  
   (λz.zy)(λz.zy)  
   (λz.zy)y  
   **yy**

5. `(λx.λy.xyy)(λy.y)y`

    (λx.λy.xyy)(λy.y)y  
    (λy.(λy.y)yy)y  
    (λy.y)yy  
    **yy**

6. `(λa.aa)(λb.ba)c`

    (λa.aa)(λb.ba)c  
    (λb.ba)(λb.ba)c  
    ((λb.ba)a)c
    **acc**

7. `(λxyz.xz(yz))(λx.z)(λx.a)`

   (λxyz.xz(yz))(λx.z)(λx.a)  
   (λyz'.(λx.z)z'(yz))(λx.a)  
   λz'.(λx.z)z'((λx.a)z)  
   λz'.z((λx.a)z)  
   **λz'.za**  
