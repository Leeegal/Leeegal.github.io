﻿---
layout: post
title: Homework1 for 系统分析与设计
date: 2018-03-15 09:30:30
categories: Software
tags: 博客
excerpt: Software
---
# 简单题

## Software Engineering Definition

* 1968年秋季，NATO（北约）的科技委员会召集了近50名一流的编程人员、计算机科学家和工业界巨头，讨论和制定摆脱“软件危机”的对策。在那次会议上第一次提出了软件工程（software engineering）这个概念，研究和应用如何以系统性的、规范化的、可定量的过程化方法去开发和维护软件，以及如何把经过时间考验而证明正确的管理技术和当前能够得到的最好的技术方法结合起来的学科。它涉及到程序设计语言、数据库、软件开发工具、系统平台、标准、设计模式等方面。其后的几十年里，各种有关软件工程的技术、思想、方法和概念不断被提出，软件工程逐步发展为一门独立的科学。

软件工程包括两种构面：软件开发技术和软件项目管理。

* 软件开发技术：软件开发方法学、软件工具和软件工程环境。
* 软件项目管理：软件度量、项目估算、进度控制、人员组织、配置管理、项目项目等。

### Software crisis

* 软件危机（英语：Software Crisis）是早期计算机科学的一个术语[1]，是指在软件开发及维护的过程中所遇到的一系列严重问题，这些问题皆可能导致软件产品的寿命缩短、甚至夭折。[2]软件开发是一项高难度、高风险的活动，由于它的高失败率，故有所谓“软件危机”之说。[3]软件危机的本源是复杂、期望和改变。这个术语用来描述正急遽增加之电脑的力量带来的冲击和可能要处理的问题的复杂性。从本质上来说，它谈到了写出正确、可理解、可验证的计算机程序的困难。

软件危机其原因，衔接到硬件的整体复杂度，与软件开发流程。危机表现在几个方面：

* 项目运行超出预算。
* 项目运行超过时间。
* 软件质量低落。
* 软件通常不匹配需求
* 项目无法管理，且代码难以维护。

硬件成长率每年大约30％，软件每年只勉强以4～7％速度在成长，信息系统的交付日期一再延后，许多待开发的软件系统无法如期开始。1960年代软件开发成本占总成本20％以下；1970年代软件成本已达总成本80％以上，软件维护费用在软件成本中高达65％。1986年公布的数据，所有验收的外包软件中，竟然只有4％可用，其余96％却是不堪一用。大部分的企业自行开发的信息系统中，有四分之三也是功败垂成。因此软件维护成本居高不下，软件产品质量低落是最主要的原因。

## COCOMO模型

COCOMO，英文全称为Constructive Cost Model，中文为结构性成本模型。它是由巴里·勃姆（Barry Boehm）提出的一种软件成本估算方法。这种模型使用一种基本的回归分析公式，使用从项目历史和现状中的某些特征作为参数来进行计算。
COCOMO模型可以分为三个层次：
* 基本COCOMO：适用对软件开发进行快速、早期地对重要的方面进行粗略的成本估计，但因其缺少不同的项目属性（“成本驱动者”）的因素，所以准确性有一定的局限性。
* 中级COCOMO：考虑进了这些成本驱动者。
* 详细COCOMO：加入了对不同软件开发阶段影响的考量。

### SDLC

软件生命周期(Software Life Cycle,SLC)又称为软件生存周期或系统开发生命周期，是软件的产生直到报废的生命周期，周期内有问题定义、可行性分析、总体描述、系统设计、编码、调试和测试、验收与运行、维护升级到废弃等阶段，这种按时间分程的思想方法是软件工程中的一种思想原则，即按部就班、逐步推进，每个阶段都要有定义、工作、审查、形成文档以供交流或备查，以提高软件的质量。

### 按照 SWEBok 的 KA 划分，本课程关注哪些 KA 或 知识领域？

* Software requirements (软件需求)
* Software design（软件设计）
* Software construction（软件构造）
* Software engineering tools and methods（软件工程工具与方法）

### 解释 CMMI 的五个级别

* level1-Initial：软件过程是无序的，有时甚至是混乱的，对过程几乎没有定义，成功取决于个人努力。管理是反应式的。
* level2-Managed：建立了基本的项目管理过程来跟踪费用、进度和功能特性。制定了必要的过程纪律，能重复早先类似应用项目取得的 成功经验。第二级共7个过程域：需求管理、项目规划、项目跟踪与控制、供应商协议管路、度量与分析、过程与产品质量保证、配置管理。
* level3-Defined：已将软件管理和工程两方面的过程文档化、标准化，并综合成该组织的标准软件过程。所有项目均使用经批准、剪裁的标准软件过程来开发和维护软件，软件产品的生产在整个软件过程是可见的。第二级共14个过程域：需求开发、技术解决方案、产品集成、验证、确认、组织过程焦点、组织过程定义、组织培训、集成项目管理、风险管理、决策分析和解决、集成团队、集成组织环境、集成供应商管理。
* level4-Quantitatively Managed：分析对软件过程和产品质量的详细度量数据，对软件过程和产品都有定量的理解与控制。管理有一个作出结论的客观依据，管理能够在定量的范围内预测性能。第四级共两个过程域：组织过程性能、量化项目管理。
* level5-Optimizing：过程的量化反馈和先进的新思想、新技术促使过程持续不断改进。第五级共两个过程域：组织创新与部署、原因分析与决策。

### 用自己语言简述 SWEBok 或 CMMI （约200字）

* CMMI全称是Capability Maturity Model Integration，即能力成熟度模型集成（也有称为：软件能力成熟度集成模型）[1]  ，是美国国防部的一个设想，1994年由美国国防部（United States Department of Defense）与卡内基-梅隆大学（Carnegie-Mellon University）下的软件工程研究中心（Software Engineering Institute，SEISM）以及美国国防工业协会（National Defense Industrial Association）共同开发和研制的，他们计划把现在所有现存实施的与即将被发展出来的各种能力成熟度模型，集成到一个框架中去，申请此认证的前提条件是该企业具有有效的软件企业认定证书。
* 其目的是帮助软件企业对软件工程过程进行管理和改进，增强开发与改进能力，从而能按时地、不超预算地开发出高质量的软件。其所依据的想法是：只要集中精力持续努力去建立有效的软件工程过程的基础结构，不断进行管理的实践和过程的改进，就可以克服软件开发中的困难。CMMI为改进一个组织的各种过程提供了一个单一的集成化框架，新的集成模型框架消除了各个模型的不一致性，减少了模型间的重复，增加透明度和理解，建立了一个自动的、可扩展的框架。因而能够从总体上改进组织的质量和效率。CMMI主要关注点就是成本效益、明确重点、过程集中和灵活性四个方面。
* CMMI是一套融合多学科的、可扩充的产品集合， 其研制的初步动机是为了利用两个或多个单一学科的模型实现一个组织的集成化过程改进。CMMI的本质是软件管理工程的一个部分。软件过程改善是当前软件管理工程的核心问题， 50多年来计算机的发展使人们认识到要高效率、高质量和低成本地开发软件，必须改善软件生产过程。基于模型的过程改进是指采用能力模型来指导组织的过程改进，使之过程能力稳定的进行改善，该组织也能变得更加成熟。


# 解释 PSP 各项指标及技能要求


* 阅读《现代软件工程》的 PSP: Personal Software Process 章节。 http://www.cnblogs.com/xinz/archive/2011/11/27/2265425.html
* 按表格 PSP 2.1， 了解一个软件工程师在接到一个任务之后要做什么，需要哪些技能，解释你打算如何统计每项数据？ （期末考核，每人按开发阶段提交这个表）

* 统计数据可以按照下表统计 

    | Personal Software Process Stages|    Time (%)  |
    | ------ | ------ |
    | 计划 |  |
    | ·         估计这个任务需要多少时间 |  |
    | 开发 |  |
    | ·         需求分析 (包括学习新技术) |  |
    | ·         生成设计文档 |  |
    | ·         设计复审 (和同事审核设计文档) |  |
    | ·         代码规范 (为目前的开发制定合适的规范) |  |
    | ·         具体设计 |  |
    | ·         测试（自我测试，修改代码，提交修改） |  |
    | 报告 |  |
    | ·         测试报告 |  | 
    | ·         计算工作量 |  |
    | ·         事后总结, 并提出过程改进计划 |  |

    ![](https://github.com/Leeegal/Leeegal.github.io/blob/master/assets/Software/psp2.1.png)