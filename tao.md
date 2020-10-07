---
title: "Mean-variance portfolio notes"
author: Xie Zejian
# date: Sep 27, 2020
output:
  pdf_document:
    toc: true
    toc_depth: 2
    # number_sections: true  
    highlight: tango
    latex_engine: pdflatex

export_on_save:
  pandoc: true
---
denoted $\delta=\mathbf{e'V^-e},\alpha=\mathbf{\overline{r}'V^-e},\xi = \mathbf{\overline{r}'V^-\overline{r}}$ where $\delta,\xi>0$ since $\mathbf{V}$ is positive define. Thus we have a linear equations:

$$ \left[\begin{array}{cc}
  \xi & \alpha\\
  \alpha & \delta
\end{array}\right]\left[\begin{array}{c}
  \lambda\\
  \gamma
\end{array}\right]=\left[\begin{array}{c}
  \overline{r}_p\\
  1
\end{array}\right]$$

Note $\delta\xi-\alpha^2>0$ since $\mathbf{(\alpha\overline{r}-\xi e)'V^-(\alpha\overline{r}-\xi e)}=\xi(\delta\xi-\alpha^2)>0$ and thus such equations is consistent.

solve and get

$$ \lambda=\frac{\delta \overline{r}_p-\alpha}{\delta\xi-\alpha^2},\gamma=\frac{\xi-\alpha\overline{r}_p}{\delta\xi-\alpha^2} $$

<!-- and

$$ \begin{aligned}
  \omega^*&=\mathbf{\lambda V^-\overline{r}+\gamma V^- e}
  \\&=\frac{\delta \overline{r}_p-\alpha}{\delta\xi-\alpha^2}\mathbf{V^-\overline{r}}+\frac{\xi-\alpha\overline{r}_p}{\delta\xi-\alpha^2}\mathbf{V^-e}
  \\&=a+b\overline{r}_p
\end{aligned} $$

where $a=\frac{\mathbf{\xi V^-e-\alpha V^- \overline{r}}}{\delta\xi-\alpha^2}$ and $b=\frac{\mathbf{-\alpha V^- e+\delta V^-\overline{r}}}{\delta\xi-\alpha^2}$ -->
