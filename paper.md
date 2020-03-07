### Recommend System

为什么要有推荐系统

先来回顾一下互联网诞生到目前为止，我们寻找信息方式的变化历程…

最早期的时候，信息是比较稀缺的，那个时候信息比较分散，寻找的效率较低，主要是人找信息。

后来信息逐渐丰富起来了，有些人或者公司专门把各种信息聚集在一个地方，人们可以通过类目导航进行查找，典型的公司是三大门户。

再后来信息量越来越大，人工添加的类目已经不能覆盖所有信息了，于是诞生了另外一种信息获取方式——搜索，典型的公司是Google、百度。

再再后来，人与信息的关系从单向的人找信息演变成了现在的双向关系，人在海量的信息中找着自己需要的东西，同时海量的信息也在找合适的人。

从这个演化过程中，我们可以看到推荐系统的出现有两个重要的前提，一个是信息过载，一个是需求不明确。随着当今技术的飞速发展，数据量也与日俱增，人们越来越感觉在海量数据面前束手无策。正是为了解决信息过载(Information overload)的问题，人们提出了推荐系统（与搜索引擎对应，人们习惯叫推荐系统为推荐引擎）。

搜索引擎更倾向于人们有明确的目的，可以将人们对于信息的寻求转换为精确的关键字，然后交给搜索引擎最后返回给用户一系列列表，用户可以对这些返回结果进行反馈，并且是对于用户有主动意识的，但它会有马太效应的问题，即会造成越流行的东西随着搜索过程的迭代会越流行，使得那些越不流行的东西石沉大海。

而推荐引擎更倾向于人们没有明确的目的，或者说他们的目的是模糊的，通俗来讲，用户连自己都不知道他想要什么，这时候正是推荐引擎的用户之地，推荐系统通过用户的历史行为或者用户的兴趣偏好或者用户的人口统计学特征来送给推荐算法，然后推荐系统运用推荐算法来产生用户可能感兴趣的项目列表，同时用户对于搜索引擎是被动的。其中长尾理论（人们只关注曝光率高的项目，而忽略曝光率低的项目）可以很好的解释推荐系统的存在，试验表明位于长尾位置的曝光率低的项目产生的利润不低于只销售曝光率高的项目的利润。推荐系统正好可以给所有项目提供曝光的机会，以此来挖掘长尾项目的潜在利润。

数量有限的情况下根本不需要推荐，用户自己就能浏览完所有的物品。再往后发展，数量级不大的情况下，人工干预就可以解决，当人工干预也无法解决时，这个时候就需要推荐系统了。

当用户需求比较明确的时候，用户会倾向于使用搜索，需求不太明确时，基于用户历史的一些行为和偏好给用户推荐一些东西能让用户先留下来，在逛的过程中可能就产生了一些新的诉求。

从以上的部分可以看到推荐系统是一个多方共赢的存在：

对用户而言，能够发现自己感兴趣的东西，提升用户体验；
对物品而言，能够发掘长尾物品的利用效率，盘活整体资源；
对平台而言，能够获取用户价值和商业价值。

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


### 评估

#### 用户满意度

点击率，用户停留时长，转化率等指标。

#### 预测准确度

分为评分预测和TopN预测。

评分预测主要是通过RMSE来衡量，即预测评分和真实评分之间的均方根误差。

TopN预测主要是用召回率和准确率来进行衡量。

召回率=推荐数与有反馈数的交集/有反馈数
准确率=推荐数与有反馈数的交集/推荐数
覆盖率

推荐系统能够推荐出来的物品，占总物品集合的比例。

#### 多样性

描述的是推荐列表中物品两两之间的不相似性，希望尽可能多的覆盖用户的兴趣点。

#### 新颖性

给用户推荐那些他们以前没有见过的东西。

#### 惊喜度

给用户的推荐结果是和用户历史上喜欢的物品不相似，但用户却又觉得满意的推荐。

#### 信任度

增加推荐系统的透明度，让用户知道推荐的理由。

比如为什么给用户推荐了这个东西，可能是历史基于历史的某次行为，也可能是基于某个好友信息…

#### 实时性

能够实时更新推荐列表，来满足用户行为的变化，能够将新加入系统的物品推荐给用户。

#### 健壮性

推荐系统抗击作弊的能力。

## Experiment

### Data Set
我们选用了来自Minnesota university的GroupLens Research 项目组的MovieLens数据集。MovieLens数据集是一个关于电影评分的数据集，里面包含了从IMDB上面得到的用户对电影的评分信息。在本论文中，我们使用MovieLens 1M数据集作为研究的数据源，其含有来自6000名用户对4000部电影的100万条评分数据。它分为三个表：电影评分、电影元数据（类型风格和年代）以及关于用户的人口统计学数据（年龄、邮编、性别和职业）。

We use the MovieLens dataset from the GroupLens Research Group at the University of Minnesota. The MovieLens 1M dataset is used as the data source in this paper. It contains 1 million ratings of 4,000 movies from 6,000 users. It is divided into three tables: movie ratings, movie metadata (genre style and age), and demographic data about users (age, zip code, gender, and occupation).

---

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