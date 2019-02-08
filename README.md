# MLND-Final-Project
Toxic Comment Classification Challenge Identify
* 代码文件: [code.ipynb](https://github.com/Zhengqi-Li/MLND-Final-Project/blob/master/code.ipynb)
* 报告文件: [机器学习工程师纳米学位毕业项目报告.pdf](https://github.com/Zhengqi-Li/MLND-Final-Project/blob/master/%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%B7%A5%E7%A8%8B%E5%B8%88%E7%BA%B3%E7%B1%B3%E5%AD%A6%E4%BD%8D%E6%AF%95%E4%B8%9A%E9%A1%B9%E7%9B%AE%E6%8A%A5%E5%91%8A.pdf)
* 输入数据下载链接：https://www.kaggle.com/c/jigsaw-toxic-comment-classification-challenge/data
* 输出文件 [best_scores](https://github.com/Zhengqi-Li/MLND-Final-Project/tree/master/best_scores) 内含文件：
    * CNN9836.csv
    * CNNRNN9844.csv
    * RNN9851.csv
    * RNNpool9851.csv
    * RNNpool9852.csv

* 本代码运行环境为Colab，默认挂载到云盘路径。若使用其他环境运行，请修改os.chdir('/content/gdrive/My Drive/comment')至目标文件夹。
* 首次运行，需下载wiki-news-300d-1M.vec文件，方法：
    * !wget https://s3-us-west-1.amazonaws.com/fasttext-vectors/wiki-news-300d-1M.vec.zip
    * !unzip 'wiki-news-300d-1M.vec.zip'
* 默认运行环境为GPU，无需另外设置。

* 训练过程中为节省运行时间，将中间结果加以保存，分别是：
    * train_test.txt - 词袋模型预处理后的训练集和测试集数据，接其后的逆文档频率分析；
    * wordvec_dict.txt - 词向量字典，接其后的分词索引；
    * input.txt - 深度模型输入数据，特征矩阵，接其后的模型训练；
    * 输出以上全部结果需花费1个小时，也可将以上中间结果隐去，重新运行。
    * 由于部分文件过大，不做提交。

* 每个模型训练结束后，可使用submission.to_csv('xxx.csv', index=False)进行保存，以使用模型融合。
* 模型融合所使用的5个结果文件包含其中，参数配置详见报告，代码展示的运行结果只是其中部分。

* 计算机配置：
    * OS：Mac OS 10.14.3
    * CPU：2.9 GHz Intel Core i7
    * Memory：16 GB 2133 MHz LPDDR3
    * GPU：Tesla K80
    * CUDA Version: 10.0 
* 训练时间（非文本处理时间）：
    * 词袋模型：500s
    * 深度模型：
        * CNN模型：240s
        * RNN模型：980s
        * CNNRNN模型：1080s
