# nlp_xiaojiang


# AugmentText
    - 回译（效果比较好）
    - EDA（同义词替换、插入、交换和删除）（）效果还行
    - HMM-marko（质量较差）
    - syntax（依存句法、句法、语法书）todo
    
# ChatBot
    - 检索式ChatBot
        - 像ES那样直接检索(如使用fuzzywuzzy)，只能字面匹配
        - 构造句向量，检索问答库，能够检索有同义词的句子
    - 生成式ChatBot（todo）
        - seq2seq
        - GAN

# FeatureProject
    - normalization_util指的是数据归一化
        - 0-1归一化处理
        - 均值归一化
        - sig归一化处理
    - sim feature（这里只有ML，没有bert、emlo等的句向量相似度）
        - distance_text_or_vec:各种计算文本、向量距离等
        - distance_vec_TS_SS：TS_SS计算词向量距离
        - cut_td_idf：将小黄鸡语料和gossip结合
        - sentence_sim_feature：计算两个文本的相似度或者距离，例如qq（问题和问题），或者qa（问题和答案）

# run(可以在win10下,pycharm下运行)
  - 1.创建tf-idf文件等（运行2需要先跑1）:  python cut_td_idf.py
  - 2.计算两个句子间的各种相似度，先计算一个预定义的，然后可输入自定义的（先跑1）:  python sentence_sim_feature.py
  - 3.chatbot_1跑起来(fuzzy检索-没)（独立）：python chatbot_fuzzy.py
  - 4.chatbot_2跑起来(句向量检索-词)（独立）：python chatbot_sentence_vec_by_word.py
  - 5.chatbot_3跑起来(句向量检索-字)（独立）：python chatbot_sentence_vec_by_char.py
  - 6.数据增强（eda)：                     python enhance_eda.py
  - 7.数据增强（marko）:                   python enhance_marko.py
  - 8.数据增强（translate_account）:       python translate_tencent_secret.py
  - 9.数据增强（translate_tools）:         python translate_translate.py
  - 10.数据增强（translate_web）:          python translate_google.py

# Data
    - chinese_vector
        - 截取的部分word2vec训练词向量（自己需要下载全效果才会好）
    - corpus
        - 小黄鸡和gossip问答预料（数据没清洗）
    - sentence_vec_encode_char
        - 1.txt（字向量生成的前100000句向量）
    - sentence_vec_encode_word
        - 1.txt（词向量生成的前100000句向量）
    - tf_idf（chicken_and_gossip.txt生成的tf-idf）
    
# requestments.txt
    - python_Levenshtei
        - 调用Levenshtein，我的python是3.6，
        - 打开其源文件https://www.lfd.uci.edu/~gohlke/pythonlibs/
        - 查找python_Levenshtein-0.12.0-cp36-cp36m-win_amd64.whl下载即可
    - pyemd
    - pyhanlp
        - 下好依赖JPype1-0.6.3-cp36-cp36m-win_amd64.whl
