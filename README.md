前期想法：
https://game.gtimg.cn/images/lol/act/img/js/heroList/hero_list.js
1.把所有的heroid数字取出
2.直接访问1到最大heroid，用HTTP状态码 判断

https://lol.qq.com/data/info-defail.shtml?id={}        heroid

https://game.gtimg.cn/images/lol/act/img/js/hero/{}.js     heroid
经过寻找，最后锁定真实url为上面这个

分析响应，截取需要的内容保存到全局list中

保存图片：
            if j < 10:
                url1 = 'https://game.gtimg.cn/images/lol/act/img/skinloading/{}00{}.jpg'.format(i,j)
                url2 = 'https://game.gtimg.cn/images/lol/act/img/skin/big{}00{}.jpg'.format(i,j)
            else:
                url1 = 'https://game.gtimg.cn/images/lol/act/img/skinloading/{}0{}.jpg'.format(i,j)
                url2 = 'https://game.gtimg.cn/images/lol/act/img/skin/big{}0{}.jpg'.format(i, j)

这里用了一个判断语句，因为分析网页发现前三位数字为英雄编号，后三位为皮肤编号，而如果皮肤编号小于10，需要手动给后三位多加个0

str = '\u9ed1\u6697\u4e4b\u5973'
str.encode('utf-8').decode('unicode_escape')

在用python做爬虫的时候经常会与到结果中包含unicode编码，需要将结果转化为中文，处理方式如上


python strip() 函数和 split() 函数的详解及实例

一直以来都分不清楚strip和split的功能，实际上strip是删除的意思；而split则是分割的意思。因此也表示了这两个功能是完全不一样的，strip可以删除字符串的某些字符，而split则是根据规定的字符将字符串进行分割。


问题：TypeError: list indices must be integers or slices, not str

解决：索引出现问题，调试步骤解决


字符串替换\n与空格
#方法
words = words.replace('\n', '').replace(' ', '')


问题：报错索引超出范围
解决：调试发现利用req_img的状态码出现判断错误，有的图片只有小图没有大图，所以导致后面的命名出现错误，利用大图req_img2判断状态码及解决。
