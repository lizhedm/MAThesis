
## Introduction

为什么要有推荐系统

回顾一下互联网诞生到目前为止我们寻找信息方式的变化历程。最早期的时候信息是比较稀缺的，信息比较分散导致寻找的效率较低，信息传递的主要方式是人找信息。后来信息逐渐丰富起来了，有些人或者公司专门把各种信息聚集在一个网址，人们可以通过类目导航进行查找。

Review the changes in the way we look for information so far since the birth of the Internet. In the earliest days, information was scarce. The scattered information led to low efficiency of searching. The main method of information transmission was that people looking for information. Later, the information has gradually been enriched. Some people or companies have gathered kinds of information on some websites, and people can search through the category navigation.

---

伴随着信息量越来越大，人工添加的类目已经不能覆盖所有信息了，于是诞生了另外一种信息获取方式——搜索，典型的公司是Google、百度。

With the increasing amount of information, artificially added categories can no longer cover all information, so another type of information acquisition way - search, is born. Typical companies are Google and Baidu.

---

通信技术和数据科学的发展，人与信息的关系从单向的人找信息演变成了现在的双向关系，人在海量的信息中找到自己需要的东西，同时海量的信息也在找与之匹配的受众。

With the development of communication technology and data science, the relationship between people and information has evolved from one-way people looking for information to the current two-way relationship. People find what they need in massive amounts of information, and at the same time, massive amounts of information are also find ways to matching with the audience.

---

从这个演化过程中，我们可以看到推荐系统的出现有两个重要的前提，一个是信息过载，一个是需求不明确。随着当今技术的飞速发展，数据量也与日俱增，人们越来越感觉在海量数据面前束手无策。正是为了解决信息过载(Information overload)的问题，人们提出了推荐系统，与搜索引擎对应，也可以称呼推荐系统为推荐引擎。

<!--need to be fixed-->

From this evolutionary process, we can see that the emergence of recommendation systems has two important prerequisites, one is information overload, and the other is ambiguous requirements. With the rapid development of today's technology and the increasing amount of data, people feel more and more helpless in the face of massive data. In order to solve the problem of information overload, the computer scientists have proposed a recommendation system, which corresponds to a search engine and can also be referred to as a recommendation engine.

---

搜索引擎要求人们有明确的目的，可以将人们对于信息的寻求转换为精确的关键字，然后交给搜索引擎最后返回给用户一系列列表，用户可以对这些返回结果进行反馈。但它会有马太效应的问题，即会造成越流行的东西随着搜索过程的迭代会越流行，使得那些越不流行的东西石沉大海。

Search engines require people to have a clear purpose. They can turn people ’s search for information into precise keywords, then give them to the search engine and finally return them to a series of lists. Users can give feedback on these results. But it will have the problem of the Matthew effect, which will cause the more popular things to become more popular as the search process iterates, making those less popular things sink to the sea.

---

而推荐引擎更适用于人们没有明确的目的，或者说他们的目的是模糊的，通俗来讲，用户连自己都不知道他想要什么，推荐系统将用户的历史行为或者用户的兴趣偏好或者用户的人口统计学特征传送给推荐算法，然后推荐系统运用推荐算法来产生用户可能感兴趣的项目列表，用户对于搜索引擎是被动的。其中长尾理论（人们只关注曝光率高的项目，而忽略曝光率低的项目）可以很好的解释推荐系统的存在，试验表明位于长尾位置的曝光率低的项目产生的利润不低于只销售曝光率高的项目的利润。推荐系统正好可以给所有项目提供曝光的机会，以此来挖掘长尾项目的潜在利润。

The recommendation engine is more suitable for people who have no clear purpose, or that their purpose is ambiguous. Generally speaking, the user does not even know what he wants. The user's historical behavior or the user's interest preferences or the user's demographic characteristics are transmitted to the recommendation system, and then the recommendation system uses some algorithm to generate a list of items that the user may be interested in. The user is passive to search engines. People only focus on high-exposure items and ignore low-exposure items, which is called the long-tail theory, can be used to explain the correctness and rationality of the recommendation system well. Experiments have shown that the low-exposure items in the long tail position generate no less than profit from selling only high-visibility items. The recommendation system can provide opportunities for all items to be recommended, for discovering the potential profits of long-tail projects.

---

当一个用户需求比较明确的时候，他会倾向于使用搜索。需求不太明确时，基于用户历史的一些行为和偏好给用户推荐一些东西能让用户先留下来，在用户浏览信息过程中可能就产生了一些新的诉求。
When a user's needs are clear, he tends to use search. When the requirements of the user are not clear, some behaviors and preferences data based on the user's history can be used to generate a pre-recommendation, to make the user stay in the system. Some new demands may arise during the user's browsing of information.

从以上的部分可以看到推荐系统是一个多方共赢的事物：

对用户而言，能够发现自己感兴趣的东西，提升用户体验；
对物品而言，能够发掘长尾物品的利用效率，盘活整体资源；
对平台而言，能够获取用户价值和商业价值。

From the above sections, we can see that the recommendation system is a multi-win-win thing:

For users, they can discover what they are interested in and improve the user experience;
For items, it is possible to discover the utilization efficiency of long-tail items and revitalize the overall resources;
For the platform, it is able to capture user value and business value.
---

### 前人研究的不足

__Explaining the inadequacies of previous studies__


Balabanovic et al. designed an adaptive agent for automated web browsing, in which we can see the prototype of the original recommendation system.

Such recommendations are unsatisfactory because they … 传统的推荐系统，也就是我们现在正大部分使用的推荐系统只是做出推荐，用户不了解推荐的原因和意义，很多时候如果推荐算法不准确，会让推荐的结果很奇怪，加深用户对推荐系统的怀疑和不信任。完全的黑盒操作，用户无法选择只能被动接受也就无法通过交互来改善推荐的效果。

Such traditional recommendation systems are unsatisfactory because most of the recommendation systems we use today only make recommendations. Users do not understand the reason and meaning of recommendations. In many cases, if the recommendation algorithm is not accurate or is completely wrong, the results of the recommendation will be strange and deepen the users' doubts and distrust. Recommendations are generated by the entire black-box operations. Users cannot choose but passively accept recommendations and cannot improve the effect of recommendation through interaction.

---

Yongfeng et al. introduced "Explainable Recommendation" which was a new survey and perspectives for recommendation system. However, much of the research up to now has been descriptive in the generation of explanation. 

后来出现了对推荐的解释研究。我们可以用解释来做什么？用户对我们的解释会作出怎样的反馈，基于这些对解释的反馈，我们可以做出哪些针对explanation的优化，如何做出这种优化？

What we can do with explanations and what feedback users can give to the system about the explanation. Based on feedback on explanations, what optimizations can the recommend system make for that and how can it make such optimizations. Little research has been done on these issues.

---


### 确定先前缺乏的研究

__Identifying the paucity or lack of previous research__



### 说明当前研究的目的

__Stating the purpose of the current research__


### 描述当前研究的局限性

__Describing the limitations of the current study__


### 概述论文或论文的结构

__Outlining the structure of the paper or dissertation__


### 这篇论文研究什么问题

说明简短论文的重点，目的或论点

__Stating the focus, aim, or argument of a short paper__


In this paper, we compare the different ways in 5 recommendation styles, provide an overview of the relationship among recommend system, recommendation explanation, and explanation adaptation. We explore the ways in which design an adaptation style for the recommendation explanation module and feedback scoring module. And we propose a new methodology for the "adaptation rule" or "adaptation algorithm" of recommendation explanation.


### 这篇文章的贡献
distribution

从Internet发展的历史过程上，思考了人与互联网络的交互方式的分类，并探讨了与搜索引擎同等量级在未来具有很大发展前景和潜力的推荐引擎研究方向。

### 为什么值得研究？

我们可以将人与Internet产生交互的场景分为三种情况：

We can divide the scenarios where people interact with the Internet into three situations:

(a)人主动使用搜索引擎查询信息,Internet根据用户搜索的内容，产生相应的搜索结果并按照某种组织结构将这个结果返回呈现出来，这个Information的体量是非常庞大和复杂的。人阅读这个Information I，并在其中尝试找到自己需要的information i，（i属于I），将其提取出来。

People proactive use search engines to get information, and the Internet generates corresponding search results based on what users search for and returns the results according to some organizational structure. The volume of this information "I" is very large and complex. People read this information "I" and try to find the information "i" they need (i belongs to I) and extract it.

(b)人输入一些信息，Internet通过推荐系统输出一些推荐，并从巨大的信息流中选取用户需要的小部分信息，发送给用户。

People enter some information, and the Internet outputs some recommendations through a recommendation system, and selects a small part of the information that the user needs from a huge information stream, and sends it to the user.

---

(c)推荐引擎主动搜索与它要推荐内容相匹配的受众以及收集Internet上用户无意识行为产生的数据并进行分析和推荐匹配。推荐引擎会主动的产生信息并将其推荐给相应的人。举例来说，一个顾客在Amazon上购买过某一件商品x，几天后，他在Youtube上观看视频，发现视频播放之前的广告是由商品x的生产企业投放的，广告内容是向他推荐与商品x类似的另一个商品y。这就是（c）交互场景简单出现在我们生活中的方式之一。未来推荐引擎基于（c）场景与人的交互方式和途径将会更加的自然和多样性。

The recommendation engine actively searches for audiences that match the content it is recommending, collects data generated by users' unconscious behaviors on the Internet, and analyzes it. In addition, it will actively generate information and recommend that to the corresponding people. For example, a customer purchased a certain product x on Amazon. After a few days, he watched the video on Youtube and found that the advertisement before the video was put by the manufacturer of product x. And the advertising content was about another product y similar to product x. This is one of the ways in which (c) interaction scenarios simply appear in our lives. In the future, human interaction approaches for the recommendation engine based on the scenario (c)  will be more natural and diverse.

---

从纵向上来分析，随着时间推移和计算机技术的发展。人的主动性在减少，相对应的，Internet的主动性在增加。这可能是未来推荐系统发展的趋势。

From a vertical perspective, over time and the development of computer technology. Human initiative is decreasing, and correspondingly, Internet initiative is increasing. This may be the trend of future recommendation system development.

---

谷歌和百度等等这些互联网巨鳄企业正是在早期依托搜索引擎技术优势，快速成长为互联网行业的巨型公司。如今的互联网技术和计算科学发展，使信息的产生和传递速度越来越快，体量越来越大，推荐系统在人们与Internaet的交互中扮演着非常重要和不可替代的作用，就如同图（b）中所描述的那样。但另一方面我们可以看到推荐引擎还有很大的发展潜力来达到和搜索引擎同等量级的重要性，就如图（c）所描述的。本文在推荐系统的explanation 和adaptation等方面做了一些有价值的研究和探索。

Internet giants such as Google and Baidu, which relied on the advantages of search engine technology in the early days, quickly grew into giant companies in the Internet industry. With the development of Internet technology and computing science today, the speed of information generation and transmission is getting faster and faster, and the volume is getting larger and larger. The recommendation system plays a very important and irreplaceable role in the interaction between people and the Internet, as described in (b). But on the other hand, we can see in (c) that recommendation engines have great development potential to achieve the same magnitude as search engines. In this paper, we will do some valuable research and exploration in aspects such as explanation and adaptation for recommend system.

---

Neural network has a pivotal role in recommend system and we use it to build a User-Movie-Neural-Network.

The "explanation" has long been a question of great interest in a wide range of fields about a recommendation system.




## Related Work

### Recommend System



---

基于内容推荐技术的纵向场景应用
以Youtube为例，每当我们看一个电影/视频时，面板的右侧都会出现推荐列表，其实这些推荐都是通过content-based方法产生的。这是充分利用到了conten-based精细化描述的优势：当用户正在观看感兴趣的视频时，他们往往更倾向于继续观看类似的内容。

基于协同过滤技术的横向场景应用
假设用户正在观看The Dark Knight，它属于蝙蝠侠题材的电影。如果我们基于内容设计推荐系统，就很可能会推荐其他的蝙蝠侠题材（或超级英雄题材）电影，而忽略了推荐影片本身的质量控制。例如，大多数喜欢The Dark Knight的人对蝙蝠侠题材和超级英雄题材的电影评价并不高，尽管他们的主角相同，题材相近。因此，这个时候有必要引入协同过滤推荐技术，以提高用户对推荐内容的惊喜度。


### Recommend System Explanation

整个推荐系统可以看作是一个加工厂，输入用户和物品数据，输出用户可能会感兴趣的物品清单，然后从物品清单中取前若干个作为推荐结果给到用户。

在这个过程中还需要做一些过滤，排序工作，输出结果的时候最好能让用户知道为什么推荐这个东西，这样用户的接受度会高一些。

---

通过一些数学算法，推测出用户可能喜欢的东西，目前应用推荐算法比较好的地方主要是网络，其中淘宝做的比较好。所谓推荐算法就是利用用户的一些行为，通过一些数学算法，推测出用户可能喜欢的东西。

推荐算法是由机器进行的，能处理大量的信息的同时，它又显得不是那么的人情化，在向用户推送的过程中难免会出现用户不再需求或者是与喜好相违背的内容，但基于机器强大的处理能力，它能处理的信息远远大于人工。

组合推荐。由于各种推荐方法都有优缺点，所以在实际中，组合推荐经常被采用。研究和应用最多的是内容推荐和协同过滤推荐的组合。最简单的做法就是分别用基于内容的方法和协同过滤推荐方法去产生一个推荐预测结果，然后用某方法组合其结果。

---

### Definition

### Graph-based Models for Explanation

Graphs can be used to represent user-user or user-item relationships in most cases. Various studies have assessed the efficacy of Graph-based Models for Explanation. Graph learning approaches such as graph-based propagation and graph clustering can be used to generate the explainable recommendations. Most research on modeling for explainable recommendation has been carried out in Graph-based model. He et al.\cite{he2015trirank} described a tripartite graph to model the user-item-aspect ternary relation for a top-N recommendation. They proposed TriRank, a common-used algorithm for ranking on tripartite graphs by regularizing and normalizing the fitting constraints and smoothness.

Based on the user-item bipartite graph for the explainable recommendation, Reinhard and his team
proposed to conduct over-lapping co-clustering, without using external information such as aspects. The users have similar interests and the items are of similar features in each co-cluster. 

Example of overlapping user-item co-clusters identified by the OC- uLaR algorithm in (Heckel et al. [2017]) 

### Graph Neural Network Algorithm

#### GCN

#### GraphSAGE 


## System Design


### MovieLens Dataset
我们选用了来自Minnesota university的GroupLens Research 项目组的MovieLens数据集。MovieLens数据集是一个关于电影评分的数据集，里面包含了从IMDB上面得到的用户对电影的评分信息。在本论文中，我们使用MovieLens 1M数据集作为研究的数据源，其含有来自6000名用户对4000部电影的100万条评分数据。它分为三个表：电影评分、电影元数据（类型风格和年代）以及关于用户的人口统计学数据（年龄、邮编、性别和职业）。

We use the MovieLens dataset from the GroupLens Research Group at the University of Minnesota. The MovieLens 1M dataset is used as the data source in this paper. It contains 1 million ratings of 4,000 movies from 6,000 users. It is divided into three tables: movie ratings, movie metadata (genre style and age), and demographic data about users (age, zip code, gender, and occupation).

---

### 4 Data Tracks

图中从MovieLens出发的两个输出，分别提取出movie table和rating table作为movie module 的输入，以及user table 作为user module的输入。用户和电影，分别代表两个路径，表示的是当系统进入一个用户或一个内容的行为轨迹。本文把整个推荐系统按照业务路径分成3个部分，分别是用户数据轨迹、电影数据轨迹以及推荐生成轨迹，接下来分别介绍下每个环节。

In the system architecture diagram. The two outputs from the MovieLens extract the movie table and rating table as the input of the movie module, and extract the user table as the input of the user module. The user and the movie, respectively, represent two paths, which represent the behavior trajectory when a user or a movie is entered in the system. This paper divides the entire recommendation system into four parts according to the business path, which are the user data track, movie data track, rating data track, and recommendation generation track. In the following paragraphs, we introduce each track separately.

---

用户轨迹方面，每次进来一名用户首先要判断这名用户是否是新用户，一旦发现是新用户将启动冷启动策略，系统会引导用户输入相关的个人信息（gender，age，occupation），然后从已有的电影数据中取出一系列top-N电影让用户选择他喜欢的电影，当选满N部电影后（在后续的prototype中，我们将N设置为10，以方便描述和测试）。系统将会以之前获得的用户个人信息和选择的N部他喜爱的电影作为输入构建用户画像，即图中的build user部分。如果用户不涉及到冷启动问题，则直接进入用户画像的构建流程，这部分用户数据是从MovieLens中user table获得的已有用户数据。综上所述，MovieLens中已有的user数据和新输入的用户数据，共同构成了系统整个的user database。

In terms of user trajectory, each time a user comes in, it is necessary to determine whether the user is a new one. Once a new user is found, a cold start strategy will be initiated. The system will guide the user to enter relevant personal information (gender, age, occupation). Then take a series of top-N movies from the existing movie data and let the user choose some movies he likes. After selecting n movies (in the subsequent prototype, we set n to 10 for easy description and testing). The system will use the previously obtained personal information of the user and the selected n favorite movies as input to build a user portrait, that is, the "Build user" part in the system architecture diagram. If the user is not involved in the cold start problem, the user goes to the "Build User" process directly. This part of the user data is the existing user data obtained from the user table in MovieLens. In summary, the existing user data in MovieLens and newly entered user data constitute the entire user database of the system together.

---

对电影进行打标，标签分两种，分别是电影自身特征（name,genre,director,actor）以及电影在系统中的行为特征。

There are two types of labeling for movies, which are the characteristics of the movie itself (name, genre, director, actor) and the behavior characteristics of the movie in the system.

电影自身特征:
Movie characteristics:

电影自身的属性，不需要频繁更新，第一次输入系统后这些数据几乎不会改变也不需要更新。电影的所属类别，电影的上映时间这些数据可以从MovieLens中获得。

The properties of the movie itself do not need to be updated frequently. These data will hardly change or need to be updated after the first input into the system. The genre of the movie and its release year can be retrieved from MovieLens.

MovieLens的电影数据并不包含电影的director,actor,writer,poster等数据，为了获得更多有用的电影元数据，从而使我们将要构造的系统能有更丰富的信息和数据展示给user，我们使用了OMDb API这个第三方服务。通过每个电影的名字和年份作为查询输入，获得该电影的director,actor,writer,poster地址等数据。将整个movie table里的所有电影对应的新数据重新整合成为一个新的movie table，构成新的movie table的数据项是：iid,title,year,genre,director,actor,writer。新的movie table构成了上图中 movie database部分。

The movie data of MovieLens does not include the director, actor, writer, poster and other data of the movie. In order to obtain more useful movie metadata, so that the system we are constructing can have richer information and data to show, we use OMDb API which is a third-party RESTful web service to get movie information. The name and year of each movie are used as query inputs to obtain the director, actor, writer, and poster addresses of the movie. The new data corresponding to all movies in the entire movie table is re-integrated into a new movie table. The data items constituting the new movie table are: (iid, title, year, genre, director, actor, writer). The new movie table constitutes the "Movie Database" part in the system architecture diagram.

---

_rating table: uid,iid,rating,timestamp,movie_count,user_count_

_movie table: iid,title,year,genre,director,actor,writer_

电影行为特征:movie behavior characteristics:

电影行为特征指的是电影内容在系统中历史被点击、评分等信息。
Movie behavior characteristics refer to information such as the movie being clicked and rated in the system.

---

当收集了电影内容以及用户特征后，就组成了内容总库以及用户总库，可以将这两个组件合并构建出模型训练集。将user database和movie database中的全部数据构造成如图所示的系统结构。rating table中的数据结构包含了某个用户对某部电影的评分，将rating table的数据作为user dataset到movie dataset的映射，将所有在rating table中有关系的user nodes 和movie nodes连接起来，连接user dataset和movie dataset的所有连线都具有weight值，其初始值设置为该user对该电影的评分。综上所述，最终构成了图中的训练集合UMNN。通过pytorch提供的一些机器学习算法，通过对UMNN进行多轮的训练后，获得一个拟合后带有新的weight值的UMNN。UMNN模型便是用来作为推荐系统的核心模块。当用户在User Interface选择N部他喜欢的电影后，User Interface将用户选择的电影id list作为输入传送给UMNN，UMNN会将推荐的id list传送给User Interface，最终User Interface显示出推荐movie id list 对应的 所有movie的信息。

When the movie and user characteristics are collected, the "Movie Database" and the "User Database" are formed. These two components can be combined to build a model training set. All data in user database and movie database are structured as shown in the figure. The data structure in the rating table contains someone user's rating of someone movie. The data of the rating table is used as a mapping from the user dataset to the movie dataset. All user nodes and movie nodes that are related in the rating table are connected. All connections in the user dataset and movie dataset have weight values, and their initial value is set to the user's rating of the movie. In summary, the training set UMNN in the system architecture diagram is finally molded. With some machine learning algorithms provided by pytorch, by multiple rounds of training on UMNN, a UMNN with a series of new weights after fitting is constructed. The UMNN model is used as the core module of the recommendation system. When the user selects N movies he likes in the User Interface, the User Interface sends the selected movie id list as input to the UMNN, and the UMNN sends the recommended id list to the User Interface, and the User Interface finally shows the recommended movies' Information.

---

### UMNN

---

### Frontend and Backend

Flask是由Python实现的一个web微框架，微框架中的“微”是指Flask旨在保持代码简洁且易于扩展，让我们可以使用Python语言快速实现一个网站或Web服务。它是目前十分流行的web框架，采用Python编程语言来实现相关web服务。主要基于 Werkzeug 和 Jinja 的轻量 WSGI Web 程序框架，Flask框架的主要特征是核心构成比较简单，但具有很强的扩展性和兼容性，程序员可以使用Python语言快速实现一个网站或Web服务。

Flask is a web micro-framework implemented by Python. The "micro" means that Flask aims to keep the code concise and easy to extend, allowing developers to quickly implement a website or web service using the Python language. It is currently a very popular web framework that uses the Python programming language to implement related web service. Based on Werkzeug and Jinja's lightweight WSGI web application framework, the main feature of the Flask framework is that the core structure is relatively simple, but has strong extensibility and compatibility. Programmers can use Python to quickly implement a website or web service.

---

和其他的轻量级框架相比较，Flask框架有很好的扩展性，拥有灵活的Jinja2模板引擎，提高了前端代码的复用率,这是其他Web框架不可替代的. 实际上，前端和后端的开发可以在Flask中用python语言一次性开发，Flask提供的template和route模块，分别充当了传统网络架构中前后端的功能。我们使用sqlite3轻量数据库来存储一些需要持久保存的数据，整个前后端以及数据库的架构非常的轻量简洁，如图所示。

Compared with other lightweight web frameworks, the Flask framework has good extensibility, has a flexible Jinja2 template engine, and improves the reuse rate of frontend code. This is irreplaceable by other web frameworks. In fact, the frontend and Backend development can be done in Flask with Python at one time. The template and route modules provided by Flask serve as the frontend and backend functions in the traditional network architecture. We use sqlite3 lightweight database to store some data that needs to be persisted. The entire frontend and backend and database architecture is very lightweight and concise, as shown in the figure.

---

在我们的整个系统中，基于机器学习的算法和数据处理操作的开发语言也是Python，这也是我们选择了可以用python作为开发语言来开发前端网页的Flask框架的原因之一。整个系统统一开发语言，这使得整个开发和后期维护变得非常的方便以及层次清晰。

In our entire system, the development language for machine learning algorithms and data processing operations is also Python, which is one of the reasons we chose it as the web development language and the Flask framework as the web framework. The entire system is developed by a unified language, which makes the whole development and later maintenance extremely convenient and clear.

---

Flask的基本模式为在程序里将一个视图函数分配给一个URL，每当用户访问这个URL时，系统就会执行在route模块该URL绑定好的视图函数，获取函数的返回值并将其显示到浏览器上，通常情况下这个返回值是已经解析好的html代码，其工作过程见图。

The basic operating mode of Flask is to assign a view function to a URL in the program. Whenever a user accesses this URL, the system will execute the view function bound to the URL in the route module, obtain the return value of the function, and display it on the browser. Usually this return value is the parsed html code. its working process is shown in the figure.

---

Web Server Gateway Interface（Web服务器网关接口，WSGI）已被用作Python Web应用程序开发的标准。 WSGI是Web服务器和Web应用程序之间通用接口的规范。

Werkzeug是一个WSGI工具包，它实现了请求，响应对象和实用函数。 这使得能够在其上构建web框架。 Flask框架使用Werkzeug作为其基础之一。

jinja2是Python的一个流行的模板引擎。Web模板系统将模板与特定数据源组合以呈现动态网页。

The Web Server Gateway Interface (WSGI) has been used as a standard for Python web application development. WSGI is a specification for a common interface between a web server and a web application.

Werkzeug is a WSGI toolkit that implements requesting service, responding objects, and building some utility functions. It makes that possible to build web frameworks on top of it. The Flask framework embeds Werkzeug as one of its foundations.

Jinja2 is a popular template engine for Python. The web template module combines templates with specific data sources to render dynamic web pages.

---

### Cold Start

从一个海量库存的内容库中，推荐系统基于用户当前上下文信息以及过去的行为给用户推荐可能喜欢的商品。如果一个用户的过去行为是空，也就是这个用户还没有过去的行为被系统记录，或者他根本就是一个新用户。这种情况下就会产生 cold start problem。

From a massive content library, the recommendation system recommends products that the user may like based on the user's current context information and past behavior. If a user's past behavior is empty, that is, the user's past behavior has not been recorded by the system, or he is simply a new user. A cold start problem occurs in this case.

---

电影推荐系统的cold start problem可以分类为new user cold start problem和new item cold start problem。

new user cold start problem：缺乏新用户的用户信息数据，缺乏人与电影的交互记录也就是访问点击和评分记录

new item cold start problem：也就是新电影加入系统后，由于缺乏访问的次数，会导致推荐不准确，甚而影响新条目获得推荐的几率，进而继续影响新条目的访问，造成负反馈。这样会导致一个流行偏见问题（popularity bias），原本受欢迎的电影获得大部分的推荐机会更受欢迎，新加入的访问记录较少的电影获得推荐的可能性更低。

The cold start problem of the movie recommendation system can be classified into new user cold start problem and new item cold start problem.

new user cold start problem: lack of personal information data for new users, lack of records of people's interaction with movies, that is, visit clicks and ratings data.

new item cold start problem: After the new movie is added to the system, due to the lack of visits, the recommendation will be inaccurate, even affects the chances of new items being recommended, and then continue to affect the access to new items, resulting in negative feedback. This will lead to a popularity bias problem. Movies that were originally popular are more likely to get most recommendations, and movies that have fewer new visits are less likely to be recommended.

---

我们的系统数据来自MovieLens，在movie数据这一部分可以直接输入MovieLens的movie数据到系统，所以本文中不涉及到new item cold start problem。在user数据这一部分，同样可以使用MovieLens的user数据作为启动数据的来源，只有在新用户使用系统时需要冷启动策略来输入数据，具体的步骤在之前的章节已经有过介绍。新用户需要输入相关的个人信息（性别，年龄，职业），并从一系列排名前N的电影中选择自己喜欢的电影。 在选择过程完成之后，输入先前获得的个人信息和所选择的n个喜欢的电影以建立用户肖像。

Our system data comes from MovieLens. For the part of movie data, the movie data from MovieLens can be directly inputted into the system, so this paper does not involve the new item cold start problem. About the user data part, the user data in MovieLens can be used as the source of startup data. Only when a new user uses this system, a cold start strategy is needed. The specific steps have been described in the previous section. To summarize, the new user needs to enter relevant personal information (gender, age, occupation) and choose some movies he likes from a series of top-N movies. After the selecting procedure is completed, the previously obtained personal information and the selected n favorite movies are inputted to build a user portrait.

---

解决cold start problem的方法通常是获得新用户的demographic data，以及引导用户与系统交互并记录用户行为，然后把用户行为属性映射到属性空间中，这样就能把新用户与老用户关联起来。也就是新的user node与movie dataset中的某一些movie node产生关联，进而也同时通过这些movie nodes与UMNN中原有的user nodes产生间接关联。

The method to solve the cold start problem is usually to obtain the demographic data of the new user, guide the user to interact with the system, record the user behavior, and then map the user behavior attributes to the attribute space. So that the new user can be associated with the existing user. That is, the new user node is associated with some movie nodes in the movie dataset, and at the same time, the new user node is indirectly associated with the existing user nodes in the UMNN by these movie nodes.

---

解决cold start problem时，通常要注意两个个问题。

When addressing cold-start issues, there are usually two problems to be aware of.

第一个难题是在冷启动推荐中的用户行为产生的数据具有稀疏的属性。在大型应用系统中，用户需要与海量的商品进行交互，对于一个特定的用户，在系统中只有很少的交互行为，与商品项之间的交互可能会更少。因此用户-商品的矩阵会非常的稀疏。针对稀疏矩阵稀疏性的处理，可以构造更为有效的数据结构，压缩稀疏行和列，或者通过PCA、SVD等方法来进行降维。

The first problem is that the data generated by user behavior, in cold start process, has sparse attributes. In large-scale application systems, users need to interact with a large number of items. For a specific user, there are only few interactions in the system, and the interaction with the item may be even less. So the user-item matrix will be very sparse. To deal with the sparseness of matrices, we can construct more efficient data structures, compress sparse rows and columns, or reduce dimensions through methods such as PCA and SVD.

---

第二个难题是效率问题，推荐系统是一个在线系统，需要具有即时性和瞬间反馈的能力，用户不希望也不接受过长的等待和过多无用的交互。我们希望引导用户进行尽量少但是足够的操作来获得尽量多而且有效的用户行为数据。既不会因为繁琐冗余的操作使用户产生不好的交互体验，又能够快速准确的构建出用户的行为画像。

The second problem is efficiency. The recommendation system is an online system. It needs the ability of immediateness and instant feedback. The user does not want or accept long waits and too many useless interactions. We want to guide users through as few as possible but sufficient operations to obtain as much and as effective user behavior data as possible. It will not cause users to have a bad interactive experience because of tedious and redundant operations, but also can quickly and accurately construct user behavior portraits.

---

### Recommendation Explanation Strategy

在构建UMNN的工作中，将user node和movie node建立连接的同时就将所有连接方式记录下。并在User Interface发送来movie id list，UMNN发送recommend id list时，把对应的连接方式作为response数据的一部分传送给User Interface。

User node和movie node建立连接的方式，我们之前在Recommendation Style章节中给出了介绍，对应每一种recommendation style都有之与其对应的Recommendation Explanation。

In the construction of UMNN, all connection methods are recorded while the user node and the movie node are connected. When the User Interface sends a movie id list and UMNN sends a recommended id list, the corresponding connection method is transmitted to the User Interface as part of the response data.

We introduced the method for establishing a connection between the User node and the movie node in the Recommendation Style section. Each recommendation style can be relevant to a Recommendation Explanation Template.

---

UserNode--MovieNode--UserNode
MovieNode--UserNode--MovieNode
DemographicFeature--UserNode--MovieNode
UserNode--MovieNode--ContentFeature

以上四种连接方式对应的四种推荐方法是user-based，item-based，demographic-based和content-based.对这四种recommendation style建立explanation template.

The four recommended methods corresponding to the above four connection methods are user-based, item-based, demographic-based, and content-based. Establish the explanation templates for these four recommendation styles.

---


* 1. user-based: (uid_1) is recommended with (iid_1) because (uid_2) is similar with (uid_1) and (uid_2) likes (iid_1). __Uid{uid-1}-Iid{iid1}-Uid{uid2}__
* 2. item-based: (iid_1) is recommended to (uid_1) because (iid_1) that is similar with (iid_2) which (uid_1) liked before. __Iid{iid1}-Uid{uid-1}-Iid{iid2}__
* 3. demographic-based: (iid_1) is recommended to (uid_1) because (uid_1)'s (DemographicFeatureType) is (DemographicFeatureValue). __Iid{iid1}-Uid{uid-1}-DFType{type}-DFValue{value}__
* 4. content-based: (uid_1) is recommend with (iid_1) because (iid_1)'s (CFtype) is (CFvalue) __Uid{uid-1}-Iid{iid}-CFType{type}-CFValue{value}__
* 5. popularity-based:

---

### Recommendation Explanation Adaptation Strategy

一个推荐系统的好坏往往需要全链路的评定，贯穿于用户的整个交互过程。之所以说好的推荐系统难以定义，是因为虽然算法是核心，但是个性化推荐往往不止由算法构成，这背后需要各种技术支撑。它是算法和各种技术架构以及交互设计等等混合在一起的产物。

The quality of a recommendation system usually requires an evaluation of the entire recommendation behavior, which runs through the user's whole interaction process. A recommendation system is good or not good, which is difficult to define. The algorithm is the core of the recommendation system, while a variety of other technologies and factors have a significant impact on personalized recommendations. The excellent recommendation system is a hybrid product of algorithms, various technics, and interaction designs.

---

从最开始信息较少时候搜索引擎的使用，到信息较多后的推荐系统的产生，再到提供更好交互体验的可解释性推荐系统，用户获取信息的方式在不断的改良和优化，我们在本文中使用了之前的论文很少研究过的adaptation这种方法，来进一步使推荐内容与用户之间的交互更多，从而使用户更活跃的参与到推荐系统的运行中，而不再是作为一个简单的信息接收者。通过让用户多伦次的使用我们的推荐系统，采集每一轮用户的行为特征输入作为正反馈来促进推荐系统的各方面性能。

From the use of search engines when there is less information at the beginning of the Internet, to the use of recommendation systems after more information appears on the Internet, to the applied of interpretable recommendation systems that provide a better interactive experience, the way users obtain information is constantly improved and optimized. In this paper, we use the adaptation method, which was rarely studied in previous related papers, to further increase the interaction between the recommended content and the user, so that the user is more actively involved in the operation of the recommendation system, instead of as a simple message receiver. By allowing users to use our recommendation system multiple times, we collect the input of user behavior characteristics for each round as positive feedback to promote various aspects of the performance of the recommendation system.

---

We find some available and reasonable recommendation explanation adaptation strategies:


---


Adaptation for the way of showing:

将explanation的显示方式进行adapt。原本系统的movie recommendation explanation是自然语言构成的可理解语句，但是有时候千篇一律的文字描述用户并没有兴趣，而且对用户来说，接收所有explanation中的文字信息并不是必要的。从语言学上我们了解到，用户只需要阅读到关键的几个词语，大多数情况下，他就已经可以通过自我串联排列扩充联想这些词语而理解到explanation需要传达的意思。

Adapt the shown of the explanation. The original movie recommendation explanation of the system is an understandable sentence using natural language, but sometimes the user is not interested in the uniform text description, and it is not necessary for the user to receive all the text information in the recommendation explanation. From linguistics, we know that the user only needs to read a few keywords, In most cases, he can connect, arrange, extend and imagine the keywords to understand the meaning of recommendation explanation.

---

接下来提出一种adaptation view的可能解决方案：使用word cloud。我们可以将电影的explanation内容与电影在wikipedia和OMDb上的metadata相结合，做一些数据处理之后，生成一个word cloud，这个word cloud可以包含许多电影的重要相关的tag或者feature，用户可以通过这个word cloud就可以在一定程度上明白推荐的理由。

We propose a possible solution for the adaptation view: use word cloud. We can combine the movie’s explanation content with the movie ’s metadata on wikipedia and OMDb. After doing some data processing, a word cloud can be generated. This word cloud could contain many important movie related tags or features. user can understand the reason for recommendation by the word cloud.

As shown in figure, there are two word clouds for the movie "Avengers Endgame" and the movie "The Dark Knight". we can respectively get the keywords from two word clouds and know the explanation of recommendation.

---

<!--建立用户5个需求level的tag cloud
自我实现 Self-actualization:
尊重 Esteem:
社交需求 Social needs:
安全需要 Safety needs:
生理需要 Physiological needs:-->

---

Adaptation by trying to insert minority items 
使系统具有推新功能
好的推荐系统是既可以根据用户的反馈来推荐，也可以不断帮助用户进行探索，因为用户可能不具有某个领域内的知识，好的推荐系统还需承载帮助用户发现新事物的功能。长尾挖掘必然是推荐需要去完成的一件事，长尾作为大头的存在，分发过程中需要将把握，或者说长尾挖掘是好的推荐系统需要去完成的任务。

---

Adaptation based on several rounds of user feedback:

这个方法的核心思想就是通过用户多轮次与推荐系统的交互，记录下每一轮的相关数据，上一轮的交互数据作为输入数据来训练并修改用户存储在系统中他的用户画像。

The core idea of this method is to record the relevant data of each round when the user interacts with the recommendation system for multiple rounds. The previous round of interaction data is used as input data to train and modify the user's portrait of the user stored in the system.

以不同推荐style的比例为例，我们可以建立这样一个adaptation rule：

Taking the ratio of different recommended styles as an example, we can establish such an adaptation rule:

	* 1
		* average_score_of_sum,   __3__
		* average_score_of_IUI,   __2__
		* average_score_of_UIU,   __1__
		* average_score_of_IUDD,  __4__
		* average_score_of_UICC   __5__  content(director,genor,...)
	
	* 2  
		* IUI + (average_score_of_IUI - average_score_of_sum) 
		* UIU + (average_score_of_UIU - average_score_of_sum)
		* IUDD + (average_score_of_IUDD - average_score_of_sum)
		* UICC + (average_score_of_UICC - average_score_of_sum)
		* if IUI or UIU or IUDD or UICC < 0, set it 0
		* if new sum != 10, make the MAX(average_score_of_XXX)++


---

## User Interface Prototype

### UI flow
总体上来说，UI的flow基本和system architecture图中的user data track一致。因此我们可以根据user data track来分析原型系统需要的输入输出数据流和其逻辑流程，并基于系统需要的功能来设计对应的模块。


### Prototype













## Experiment

### User Study Process


### 评估
system evaluation


#### 用户满意度 
satisfaction

点击率，用户停留时长，转化率等指标。
question 8.

#### 预测准确度
accuracy

question 9. 10. 

#### adaptation有效性
adaptation effectiveness
question (11.12.13)

分为评分预测和TopN预测。

评分预测主要是通过RMSE来衡量，即预测评分和真实评分之间的均方根误差。

TopN预测主要是用召回率和准确率来进行衡量。

准确率=推荐数与有反馈数的交集/推荐数

覆盖率

推荐系统能够推荐出来的物品，占总物品集合的比例。

#### 多样性
Diversity
question 14

描述的是推荐列表中物品两两之间的不相似性，希望尽可能多的覆盖用户的兴趣点。

#### 新颖性
Novelty
question 15

给用户推荐那些他们以前没有见过的东西。

#### 惊喜度
Surprise
question 16

给用户的推荐结果是和用户历史上喜欢的物品不相似，但用户却又觉得满意的推荐。

#### 信任度
Trust
question 17
增加推荐系统的透明度，让用户知道推荐的理由。

比如为什么给用户推荐了这个东西，可能是历史基于历史的某次行为，也可能是基于某个好友信息…

#### 实时性

能够实时更新推荐列表，来满足用户行为的变化，能够将新加入系统的物品推荐给用户。

#### 健壮性

推荐系统抗击作弊的能力。

---

这说明，在我们20人的user study样本空间中。测试者通过三轮的explanation adaptation，平均的评分提升了。

This shows that in our user study, the average score of users improved through three rounds of explanation adaptation.

#### Accuracy
对比关于accuracy的3个问题：Q7，Q9和Q10，我们可以发现一个非常有趣的现象。有部分user表示推荐系统推荐了正确的电影给他们，但是他们却认为推荐系统并没有推荐他们真正期待和想要的电影。

Comparing the three questions about accuracy ( Q7, Q9, Q10), we can find a very interesting phenomenon. Some users said that the recommendation system recommended the right movies to them, but they thought that the recommendation system did not recommend the movies they really expected and needed.

---

大多数推荐系统，包括我们的推荐系统，都往往是基于一些数据和记录来推荐用户可能感兴趣的事物，这当然是正确的推荐，但有些时候这种推荐可能并不是用户真正期待和需求的。推荐的事物只满足了用户的physiological needs, safety needs, social needs。而更高层次的esteem and self-actualization needs可能会成为未来推荐系统可能的发展发向之一。

Most recommendation systems, including our recommendation system, often recommend things that users may be interested in based on some data and records. This is certainly the right recommendation, but sometimes it may not be what users really expect and demand. The recommended things only satisfy the user's physiological needs, safety needs, and social needs. And higher-level esteem and self-actualization needs may become one of the possible development directions of future recommendation systems research area.

---

## Conclusion

我们已经明白推荐解释对于推荐系统的重要性。目前的很多商用的推荐系统很少提供解释，即使提供推荐解释，大多数只是采用单一简陋的解释机制。而且这些推荐解释，并没有被充分利用来提升推荐系统的性能。

在本文中，我们通过实验印证了对推荐系统的可解释性的研究有助于推荐系统与用户更好的交互，从而产生准确有效可信任的推荐。

未来可解释推荐系统的研究发展方向，可以朝着以下几个方面发展：

1.智能化，可视化

现在的推荐解释更多使用简单的文字解释来呈现，对于海量信息推荐系统来说，文字呈现出的解释内容必然也会体量巨大，比如用户浏览一个购物网站，每一件商品的推荐解释可能只有3行文字，但如果几百个商品同时展示给用户并附上每个商品的推荐解释，用户要接收的数据量就非常巨大了。这某种程度上影响了对用户的友好度，并大大降低了推荐解释的效率。

通过可视化解释内容来减少用户的信息接收负担。随着推荐越来越精准，越来越个性化，推荐解释的内容表达将会更加智能化，更接近于用户容易理解的自然语言，以此强化与用户的交互，有效提高用户的信任程度和满意度。

2.设计解释时考虑更全面

系统设计者在设计推荐解释时，为了使得解释能够更好地促进推荐系统提升效用，除了考虑解释自身的评估标准，明确解释欲发挥的目标作用外，还要将推荐系统的展现方式、用户与解释的交互方式等方面考虑在内。

3.分类更加细化

随着推荐系统的不断发展，当新型的推荐算法出现时，新的解释类型也随之登场。为了让推荐解释分类能够更加一般化，能够囊括全新的解释类型，解释的分类维度将需要进一步扩充，而不单单只是基于用户、产品和内容特征三者。可能将来还会加入如时间、地点、情感等新的维度。

4.更深入研究不同解释间的性能比较

目前虽然有了对推荐解释的评估标准，但针对不同解释类型间基于不同目标作用的性能比较，这方面的研究成果仍然比较欠缺。而如果能够准确地对比不同解释类型在不同需求下的优劣差异，那么将有利于系统设计者能够更加准确地为不同推荐系统选择恰当的推荐解释。

5.解释界面更加创新

未来将有更多研究工作会集中在新型的解释界面上，让解释能显得更加直观，更加易懂。下图是一款名为“Treemap”的新型解释界面，用不同的颜色种类，颜色亮度和方格大小来区分不同推荐项目的优先程度。