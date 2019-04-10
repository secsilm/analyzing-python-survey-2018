# Analyzing python survey 2018

## 前言

2018 年秋季，PSF（Python Software Foundation，Python 软件基金会）和 JetBrains 一起进行了第二次全球范围内的关于 Python 使用情况的问卷调查，共有来自 150 多个国家的 19835 名开发者参与了这次调查，[官方](https://www.jetbrains.com/research/python-developers-survey-2018/)也发布了一份调查报告分析。

我之前也对 [2017 年的调查结果进行了简单分析](https://alanlee.fun/2018/04/28/analyzing-python-survey-2017/)，主要分析了 Python 3 的使用情况（再一次建议大家使用 Python 3，Python 2 在 2020 年就要停止维护，所以无论如何，GO PYTHON 3！）。这次呢，我也主要沿着 2017 的分析结果走，也可以做个对比（当然主要是时间有限，光是这个就已经拖了很久了 😂）。

之后还可能加入其他分析，这些会及时更新在 [GitHub](https://github.com/secsilm/analyzing-python-survey-2018) 上，上面也包含了[问卷调查的内容（PDF）](./Python_developers_survey_2018_questions.pdf)和[调查结果原始数据（CSV）](./python_psf_external_18.csv)：

<div class="github-card" data-github="secsilm/analyzing-python-survey-2018" data-width="500" data-height="155" data-theme="default"></div>
<script src="//cdn.jsdelivr.net/github-cards/latest/widget.js"></script>

此外，也可以在 Colab 和 Jupyter nbviewer 上查看代码：

- Jupyter nbviewer：[analyzing-python-survey-2018.ipynb](https://nbviewer.jupyter.org/github/secsilm/analyzing-python-survey-2018/blob/master/analyzing-python-survey-2018.ipynb)
- Colab：[analyzing-python-survey-2018.ipynb - Colaboratory](https://colab.research.google.com/github/secsilm/analyzing-python-survey-2018/blob/master/analyzing-python-survey-2018.ipynb)

## 数据

先来看下我们的调查结果数据：

![](https://i.imgur.com/nnlXCtD.png)

数据总大小是 19835×283，即 19835 行 283 列，上图是随机的一行，每行代表一个样本，即一个参与调查的开发者。可以看到已经将一道选择题的答案拆分成多列，这一般是用于处理多选题，例如上图中的「java:what other language(s) do you use?」，而单选题则不用拆分，可以直接写答案，例如上图第一列。

其实官方公布的参与调查人数是 2 万多，但是这里看到调查结果是不到 2 万，我个人觉得应该是剔除了一些无效问卷。单从参与调查人数上来说，2018 年已经是 2017 年的两倍了，当然 2018 年的调查我也参与了 😃

## 问题

去年分析（2018）的问题：

- 使用 Python 2 和 Python 3 的开发者的比例？
- 做数据分析和机器学习的人中分别有多少人使用的是 Python 3？
- 常用框架中使用 Python 2 和 Python 3 的比例？
- 做数据分析和机器学习的人常用的框架？
- 公司规模大小和是否使用 Python 3 的关系？
- 开发者年龄和是否使用 Python 3 的关系？
- 使用 Python 3 和 Python 2 的开发者的国别分布？
- 开发者中使用 IDE 的情况？

今年分析（2019）新增问题：

- 使用最多的 Python 2/Python 3 版本

## 简单结论

- Python 3 的使用人数确实在快速增长，从 75% 到 84%
- 越来越多做数据分析的人在使用 Python 3，比去年增长 10%
- 无论是机器学习还是数据分析，numpy 和 pandas 依然是重头
- 美国的开发者年龄结构依然好于中国
- 参与调查的中国开发者人数这两年并无太大变化，但是总人数排名上从第三跌到第五
- VSCode 和 Jupyter Notebook 越来越成为主流的开发工具，VSCode 更是从第六升至第二（使用人数）
- Python 2 中使用最多的是 Python 2.7，Python 3 中使用最多的是 Python 3.6