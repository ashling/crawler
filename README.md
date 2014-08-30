## 开发环境
- Python 2.7 
## 功能  
- 支持从json文件读取抓取任务
- 支持对同一个url连接的id爬虫
- 抓取网页与网页解析是异步处理
- 使用requests抓取网页  

## 软件安装  
## 语法格式  
- json对象示例  
\#这是个示例文件   
\#里面所有的模块文件都固定保存在 当前目录下的module目录下   

\{  
"action" : "main" ,  
> "name":  "application name" ,  
>> "subaction": \[  
>> \{  
>>> "action" : "fetcher" ,  
>>> "urlprefix": "http://suixinkan.baidu.com/guess/detail/detail_page?mid=" , #url前缀  
>>> "urlsuffix" :  "\${%data/idfile}"  , #all id files   
>>> "headers" :   
>>> \{   
>>>> "User-Agent": "Mozilla/4.0" ,  
>>>> "Host": "suixinkan.baidu.com"  ,  
>>>> "Connection": "Keep-Alive"  ,   
>>>> "Cookie":"Hm_lvt_378678e15"   
>>> \} ,  
>>> "initmodule" : "initheader" ,  #初始化模块,即为ashmodules中的一个函数名，自定义 http 协议的头部。"	       
>>> outputdir" : "data/htmls" ,  
>>> "savefilename" : "${urlsuffix}" ,  #每一个网页保存到一个名为url 后缀  
>>> "subaction": [   
>>> \{  
>>>> "action" : "parser" ,   
>>>> "parsermodule" : "parserhtml", #格式：modulename.classname   
>>>> "outputfile": "data/outputfilename"   
>>> \}   
>>> ]   
>> \}   
>> ]   
\}   
