---
layout: post
title:  "GitHub pages에 수식 사용 설정 및 입력 방법"
subtitle: ""
date:   2018-01-20 18:00:00 +0900
background: '/img/posts/06.jpg'
---

## 설정

* `_config.yml`

  ```
  kramdown:
    math_engine: mathjax
  ```

  출처: [Kramdown](https://kramdown.gettalong.org/options.html)

* `_includes/scripts.html`

  ```html
  <script type="text/x-mathjax-config">
    MathJax.Hub.Config({
      TeX: {
        equationNumbers: {
          autoNumber: "AMS"
        }
      },
      tex2jax: {
        inlineMath: [ ['$','$'], ["\(","\)"] ],
        displayMath: [ ['$$','$$'], ["\[","\]"] ],
        processEscapes: true
      }
    });
  </script>
  <script type="text/javascript" async
    src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.2/MathJax.js?config=TeX-MML-AM_CHTML">
  </script>
  ```

  참고: `TeX-MML-AM_CHTML` 설정은 아래 코드와 동일함

  ```javascript
  MathJax.Hub.Config({
    jax: ["input/TeX","input/MathML","input/AsciiMath","output/CommonHTML"],
    extensions: ["tex2jax.js","mml2jax.js","asciimath2jax.js","MathMenu.js","MathZoom.js","AssistiveMML.js", "a11y/accessibility-menu.js"],
    TeX: {
      extensions: ["AMSmath.js","AMSsymbols.js","noErrors.js","noUndefined.js"]
    }
  });
  ```

  출처: [MathJax](http://docs.mathjax.org/en/latest/start.html)


## 입력 방법

* displayMath: `$$`, `$$` 쌍 사용

  입력:

  ```
  $$ x_a = y_c $$
  ```

  표시:

  $$ x_a = y_c $$


* displayMath: `\[`, `\]` 쌍 사용

  입력:

  ```
  \[ x_a = y_c \]
  ```

  표시:

  \[ x_a = y_c \]


* inlineMath: `$`, `$` 쌍 사용

  입력:

  ```
  inline: $x_a = y_c$
  ```

  표시:

  inline: $x_a = y_c$


* inlineMath: `\(`, `\)` 쌍 사용

  입력:

  ```
  inline: \(x_a = y_c\)
  ```

  표시:

  inline: \(x_a = y_c\)


* 그릭 문자, 기호 사용

  입력:

  ```
  $$
  \psi_0 = a + b
  $$
  ```

  표시:

  $$
  \psi_0 = a + b
  $$


* 수식 번호 부여

  입력:

  ```
  \begin{equation}
    \psi_1 = a + b
  \end{equation}
  ```

  표시:

  \begin{equation}
    \psi_1 = a + b
  \end{equation}


* 수식 번호 부여, 여러 수식, 정렬

  입력:

  ```
  \begin{align}
    \psi_2 &= a + b  \\\\ 
    \psi_3 + \phi_4 &= c
  \end{align}
  ```

  표시:

  \begin{align}
    \psi_2 &= a + b  \\\\ 
    \psi_3 + \psi_4 &= c
  \end{align}


* 수식 번호 없게, 여러 수식, 정렬

  입력:

  ```
  \begin{align\*}
    \psi_4 = a + b  \\\\ 
    \psi_5 = ab
  \end{align\*}
  ```

  표시:

  \begin{align\*}
    \psi_4 = a + b  \\\\ 
    \psi_5 = ab
  \end{align\*}
