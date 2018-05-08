# 2018-02-11 Python Crash Course



**Book Name:** 
![](https://ws2.sinaimg.cn/large/006tNc79ly1fp3bydfkmhj30f106gt9h.jpg)
Python Crash Course
A Hands-On, Project-Based Introduction to Programming


**Python**  /ˈpaɪ.θɑːn/  美式发音读起来很酷也很专业. 
1. 助记,
Python是编程语言的名字,没有任何实际意义,相当于张三李四.
是语言作者最喜欢的一个英国马戏团的名字,同时也是一种蟒蛇的名字.
我编了喜欢的名字:
Py(圆周率的π) + thon(song)
Py + Song.  圆周率之歌. Song of Py.

**Crash course** 速成班
1. 助记, 略
2. 词源,略
3. 释义, 
速成班；短训班；速成教程: A course that teaches you a lot of basic facts in **a very short time**

**Hands-On** 动手的, 实操的
1. 助记, 
动手的, 把双手放在上面,让手参与进来. Hands on
2. 词源,略
3. 释义,
1) 亲身实践的 (PRACTICAL EXPERIENCE)
Someone who has hands-on experience of something has done or used it rather than just read or learned about it.
2) 事事过问的，事必躬亲的 (INVOLVED)
Someone with a hands-on way of doing things becomes closely involved in managing and organizing things and in making decisions.
**Computing** Involving or requiring personal operation at a keyboard.

**Project** /ˈprɑː.dʒekt/ 项目
1. 助记
Pro(forwards) + ject(throw)
Project is Plan ,the thing you throw forwards to the future from today.
因此Projector是投影仪.
项目的定义的内涵和外延,广泛且庞杂(参考拓展)
但在计算机领域极为简单,Project是case(案例)的替代词汇.
比如写一个程序计算1+1 =2,可以说是一个计算1+1= 2的project或者program.
Python的完整且最为繁琐的一种代码写法如下:
```pyhton
result = 1 + 1
print(result)
```
2. 词源
Meaning **"scheme, proposal, mental plan"** 
 From Latin projectum ‘something prominent’,\
From pro- ‘forth’ + jacere ‘to throw’
**OED Origin**
Late Middle English (in the sense ‘preliminary design, tabulated statement’): from Latin projectum ‘something prominent’, neuter past participle of proicere ‘throw forth’, from pro- ‘forth’ + jacere ‘to throw’. Early senses of the verb were ‘plan’ and ‘cause to move forward’.
**Etymology**
c. 1400, "a plan, draft, scheme," from Latin proiectum "something thrown forth," noun use of neuter of proiectus, past participle of proicere "stretch out, throw forth," from pro- "forward" (see pro-) + combining form of iacere (past participle iactus) "to throw" (from PIE root *ye- "to throw, impel").
Meaning **"scheme, proposal, mental plan"** is from c. 1600. Meaning "group of low-rent apartment buildings" first recorded 1935, American English, short for housing project (1932). Related: Projects. Project manager attested from 1913.
3. 释义
	1. Noun:
 1) 项目；方案；工程 , a piece of planned work or an activity that is finished over a period of time and intended to achieve a particular purpose
 2)（尤指学生做的）课题，研究, a study of a particular subject done over a period of time, especially by students
	2. Verb
1) (CALCULATE) 预计,估算
	​to calculate an amount or number expected in the future from information already known
	Government spending is projected to rise by three percent next year. 明年政府的支出预计将增加3%。
2) 投掷；发射(THROW)
	[ T ] to throw or direct something forwards, with force
3) 放映；投射（影、像或光） (MAKE AN IMAGE)
		 T ] to cause a film, image, or light to appear on a screen or other surface	 
4. 拓展,
**PMBOK** 美国项目管理协会的定义
> A project is a **temporary** endeavor undertaken to create **a unique product, service, or result.**   
> 项目定义的三个特性:  
> 1) The **temporary** nature of projects (临时性)  
> indicates that a project has a definite beginning and end. The end is reached when the project’s objectives have been achieved or when the project is terminated because its objectives will not or cannot be met, or when the need for the project no longer exists. A project may also be terminated if the client (customer, sponsor, or champion) wishes to terminate the project. Temporary does not necessarily mean the duration of the project is short. It refers to the project’s engagement and its longevity. Temporary does not typically apply to the product, service, or result created by the project; most projects are undertaken to create a lasting outcome. For example, a project to build a national monument will create a result expected to last for centuries. Projects can also have social, economic, and environmental impacts that far outlive the projects themselves.  
> 2) Every project creates a **unique product, service, or result.** (Deliverable, 可交付性)  
> The **outcome** of the project may be tangible or intangible. Although repetitive elements may be present in some project deliverables and activities, this repetition does not change the fundamental, unique characteristics of the project work. For example, office buildings can be constructed with the same or similar materials and by the same or different teams. However, each building project remains unique with a different location, different design, different circumstances and situations, different stakeholders, and so on.  
> 3) **Unique**(独特性)  
> An ongoing work effort is generally a repetitive process that follows an organization’s existing procedures. In contrast, because of the unique nature of projects, there may be uncertainties or differences in the products, services, or results that the project creates. Project activities can be new to members of a project team, which may necessitate more dedicated planning than other routine work. In addition, projects are undertaken at all organizational levels. A project can involve a single individual or multiple individuals, a single organizational unit, or multiple organizational units from multiple organizations.  
**Wikipedia**
> In contemporary business and science, a project is an individual or collaborative enterprise, possibly involving research or design, that is carefully planned, usually by a project team, to achieve a particular aim.[1]  
> A project may also be a set of interrelated tasks to be executed over a fixed period and within certain cost and other limitations.[2]  
> It may be a temporary (rather than permanent) social systems as work systems that is constituted by teams within or across organizations to accomplish particular tasks under time constraints.[3] A project may be a part of a wider programme management  


**Introduction**
1. 助记,
Intro(inward) + duct(lead, conduct) + ion
往里领进来.
2. 词源,
From intro- "inward, to the inside" (see intro-) + ducere "to lead," from PIE root ***deuk-** "to lead."
**Origin**
Late Middle English (in the sense ‘bring (a person) into a place or group’): from Latin introducere, from intro- ‘to the inside’ + ducere ‘to lead’.
**Etymology**
late 14c., "act of bringing into existence," from Old French introduccion (14c.) and directly from Latin introductionem (nominative introductio) "a leading in," noun of action from past participle stem of introducere "to lead in, bring in; introduce; found, establish; bring forward (as an assertion)," from intro- "inward, to the inside" (see intro-) + ducere "to lead," from PIE root *deuk- "to lead."
Meanings "initial instruction in a subject" and "an introductory statement" are from mid-15c.; meaning "elementary treatise on some subject" is from 1520s. The sense of "formal presentation of one person to another" is from 1711.
3. 释义,​
1) 入门（图书，课程）(BASIC KNOWLEDGE)
​a book or course that provides basic knowledge about a subject
2) 首次（经历，接触某事） introduction noun (FIRST EXPERIENCE)
​the first time someone experiences something
3) 开始 (BEGINNING) the first part of something
4) 介绍,引荐introduction noun (GIVING SB'S NAME)
the action of telling someone another person's name the first time that they meet
5) 采用；引进；推行；放入，插入
an occasion when something is put into use or brought to a place for the first time


Programming == Coding 编程
1. 释义, 
- **Wikipedia**: the act of instructing computers to perform tasks
- **Cambridge** (计算机的）程序 the activity or job of writing computer programs
2. 拓展放在文末.

- 总结
Python Crash Course( Python速成课)
A Hands-On, Project-Based Introduction to Programming
(实操的,基于项目的编程入门)
 Python速成课, 基于项目与实操的编程入门

## 深入拓展
**Crash** US ​  /kræʃ/
1. 助记, 
 "break in pieces;”Crash into pieces
3. 词源, 
 "break in pieces;"
**OED Origin**
Late Middle English: imitative, perhaps partly suggested by **craze and dash**.
**Etymology**
*crash (v.)*
late 14c., crasschen "break in pieces;" probably imitative. Meaning "break into a party, etc." is 1922. Slang meaning "to sleep" dates from 1943; especially from 1965. Computing sense is from 1973. Related: Crashed; crashing.
*crash (n.)*
1570s, from crash (v.); sense of "financial collapse" is from 1817, "collision" is from 1910; references to falling of airplanes are from World War I.
3. 释义, 
1) 迅速全面的；速成的；应急的  Quick and involving a lot of effort
2) 动词,  撞（车）；撞毁，撞坏；坠毁, 
If a vehicle crashes or someone crashes it, it is involved in an accident, usually a serious one in which the vehicle is damaged and someone is hurt.
3) （使）猛撞（常发出巨大声响或造成破坏） 
to hit something, often making a loud noise or causing damage
4) Fail, （公司等）垮台，破产，崩溃，崩盘
（计算机或系统）瘫痪，死机, If a computer or system crashes, it suddenly stops operating.


**Course**
1. 助记, 
Course (Current, 水流,溪流)
Flow of a river
课程的安排如流水一般.
2. 词源
 From curs- past participle stem of currere "to run" (from PIE root *kers- "to run").
词源是流水.
**OED Origin**
Middle English: from Old French cours, from Latin cursus, from curs- ‘run’, from the verb currere.
**Etymology**
late 13c., "onward movement," from Old French cors (12c.) "course; run, running; flow of a river," from Latin cursus "a running race or course," from curs- past participle stem of currere "to run" (from PIE root *kers- "to run").
Most extended senses (meals, etc.) are present in 14c. Academic meaning "planned series of study" is c. 1600 (in French from 14c.). Phrase of course is attested from 1540s; literally "of the ordinary course;" earlier in same sense was bi cours (c. 1300).
3. 释义
1) 课程；教程 a set of classes or a plan of study on a particular subject, usually leading to an exam or qualification
4. 拓展, 词根
> *kers-  
> Proto-Indo-European root meaning "to run."  
> It forms all or part of: **car; career; cargo**; caricature; cark; **carpenter; carriage; carrier; carry**; charabanc; charette; charge; chariot; concourse; concur; concurrent; corral; corridor; corsair; courant; courier; **course; currency; current**; curriculum; cursive; cursor; cursory; discharge; discourse; encharge; excursion; hussar; incur; intercourse; kraal; miscarry; occur; precursor; recourse; recur; succor.  


**Base**
1. 助记
foundation 
2. 词源
**OED Origin**
Middle English: from Old French, from Latin basis ‘base, pedestal’, from Greek.
"starting point"
**Etymology**
"bottom of anything considered as its support, foundation, pedestal," early 14c., from Old French bas "depth" (12c.), from Latin basis "foundation," from Greek basis "a stepping, a step, that on which one steps or stands, pedestal," from bainein "to go, walk, step," from **PIE root *gwa- "to go, come."**
The military sense "secure ground from which operations proceed" is from 1860. The chemical sense "compound substance which unites with an acid to form a salt" (1810) was introduced in French 1754 by French chemist Guillaume-François Rouelle (1703-1770). Sporting sense of "starting point" is from 1690s, also "destination of a runner" (1812). As a "safe" spot in a tag-like or ball game, suggested from mid-15c. (as the name of the game later called prisoner's base). Hence base-runner (1867), base-hit (1874), etc. Meaning "resources on which something draws for operation" (as in power-base, database, etc.) is by 1959.
3. 释义
1) 基底，底座；底层，底子(BOTTOM) the bottom part of an object, on which it rests, or the lowest part of something
2) 总部, 基地, the main place where a person lives and works, or a place that a company does business from
动词,  以…为基础.
Use (something specified) as the foundation or starting point for something.

**Program**
1. 助记,
 From pro ‘before’ + graphein ‘write’.
Pro(before) + writing
Program就是事先(before)写好的things, 等着去被执行.
```python
result = 1 + 1
print(result)
# 这是程序, 事先写好的.
In [4]: print(result)
2
这是运行后,得出结果.
```
Pro + gram 事先写好的文字.
2. 词源,
牛津词源将Pro解释成before比forth有说服力
**OED Origin**
Early 17th century (in the sense ‘written notice’): via late Latin from Greek programma, from prographein ‘write publicly’, from pro ‘before’ + graphein ‘write’.
**Etymology**
1630s, "public notice," from Late Latin programma "proclamation, edict," from Greek programma "a written public notice," from stem of prographein "to write publicly," from pro "forth" (see pro-) + graphein "to write" (see -graphy).
	General sense of "a definite plan or scheme" is recorded from 1837. Meaning "list of pieces at a concert, playbill" first recorded 1805 and retains the original sense. That of "objects or events suggested by music" is from 1854. Sense of "broadcasting presentation" is from 1923. Computer sense (noun and verb) is from 1945. Spelling programme, established in Britain, is from French in modern use and began to be used early 19c., originally especially in the "playbill" sense. Program music attested from 1877.
> -graphy  
> word-forming element meaning "process of writing or recording" or "a writing, recording, or description" (in modern use especially in forming names of descriptive sciences), from French or German -graphie, from Greek -graphia "description of," used in abstract nouns from graphein "write, express by written characters," earlier "to draw, represent by lines drawn," originally "to scrape, scratch" (on clay tablets with a stylus), from PIE root *gerbh- "to scratch, carve" (see carve).  
3. 释义,
1)  （计算机）程序；编码指令
	a series of instructions that can be put into a computer in order to make it perform an operation
```pyhton
1 + 1
# 这就是指令(instructions)
```

Programming:
维基百科中的详细定义.
[Computer programming - Wikipedia](https://en.wikipedia.org/wiki/Computer_programming)	
> Computer programming (often shortened to programming) is a process that leads from an original formulation of a computing problem to executable computer programs. Programming involves activities such as analysis, developing understanding, generating algorithms, verification of requirements of algorithms including their correctness and resources consumption, and implementation (commonly referred to as coding[1][2]) of algorithms in a target programming language. Source code is written in one or more programming languages. The purpose of programming is to find a sequence of instructions that will automate performing a specific task or solving a given problem. The process of programming thus often requires expertise in many different subjects, including knowledge of the application domain, specialized algorithms, and formal logic.  







