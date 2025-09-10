---
title: "Теория вероятностей и математическая статистика"
subtitle: "Полная вероятность. Формула Байеса. Случайные величины."
institute: "ВШБ Бизнес-информатика"
author: "Глеб Карпов"
format: 
    beamer:
        pdf-engine: xelatex
        aspectratio: 169
        fontsize: 9pt
        theme: Singapore
        fonmttheme: serif
        section-titles: true
        incremental: true
        include-in-header: ../files/xeheader.tex  # Custom LaTeX commands and preamble
---

## Полная вероятность

* Концепция условной вероятности неразрывно связана со следующей идеей *полной* вероятности.

* Рассмотрим зафиксированное пространство $\left( \Omega, \mathcal{F}, P \right)$. Назовем **разбиением** $\Omega$ коллекцию событий $\{ B_k, \, k \in I \}$, таких что $B_i \cap B_j = \varnothing$ при $i \neq j$ и $\bigcup B_i = \Omega$.

* Вдобавок, рассмотрим какое-то другое событие $B$, которое пересекается с какими-то событиями из разбиения, но не обязано пересекаться со всеми.

\begin{tikzpicture}
    % Рисуем прямоугольник 10x4
    \draw[thick] (0,0) rectangle (10,4);
    
    % Разделяем на 5 вертикальных секторов (каждый шириной 2)
    \draw[thick] (2,0) -- (2,4);
    \draw[thick] (4,0) -- (4,4);
    \draw[thick] (6,0) -- (6,4);
    \draw[thick] (8,0) -- (8,4);
    
    % Заливаем секторы разными цветами
    \fill[red!20] (0,0) rectangle (2,4);
    \fill[blue!20] (2,0) rectangle (4,4);
    \fill[green!20] (4,0) rectangle (6,4);
    \fill[yellow!20] (6,0) rectangle (8,4);
    \fill[purple!20] (8,0) rectangle (10,4);
    
    % Рисуем эллипс, который пересекает все секторы кроме первого
    \draw[thick] (6,1.5) ellipse (4 and 1.5);
    
    % Подписываем секторы
    \node at (1,3.5) {$B_1$};
    \node at (3,3.5) {$B_2$};
    \node at (5,3.5) {$\ldots$};
    \node at (7,3.5) {$B_{n-1}$};
    \node at (9,3.5) {$B_n$};
    
    \node at (6.5,1) {$A$};
    \node[above] at (5,4.2) {$\Omega$};
\end{tikzpicture}

## Полная вероятность

:::{.callout-theorem}
Если $\{B_1, B_2, \ldots \,  \}$ - разбиение $\Omega$, c $P(B_i) > 0 \; \forall i$, то:

$$
    \boxed{P(A) = \sum \limits_{i} P(A|B_i) P(B_i), \, \forall A \in \mathcal{F}}   
$$

**Доказательство.** Заметим, что мы можем реконструировать событие $A$ из его частичек-пересечений со всеми $B_i$: $A = \bigcup\limits_{i} (A \cap B_i)$. Эти кусочки $\{ A \cap B_i  \}$ попарно не пересекаются, как и оригинальные элементы разбиения. Поэтому далее можем применить свойство аддитивности вероятности:

\begin{gather*}
P(A) = P \left( \bigcup\limits_{i} (A \cap B_i) \right) \\
= \sum \limits_{i} P \left(A \cap B_i \right)
= \sum \limits_{i} P(A|B_i) P(B_i)
\end{gather*}
:::

## Теорема Байеса

$$
\boxed{ P(B_j|A) = \frac{P(A|B_j)P(B_j)}{\sum \limits_{i} P(A|B_i) P(B_i)} }
$$

Let us recall definition of conditional probability:

$$
    P(A|B) = \frac{P(A \cap B)}{P(B)}
$$

We can notice that probability of intersection $(A \cap B)$ may be
written in two ways:

$$
P(A \cap B) = P(A|B) P(B) = P(B|A) P(A),
$$

which gives us a formula, how two 'inverted' conditional probabilities
are connected:

$$
P(B|A) = \frac{P(A|B) P(B)}{P(A)}.
$$

## Пример

## Случайные величины

##
