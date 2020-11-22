# Java_5
## 实验目的
1. 掌握字符串String及其方法的使用。
2. 掌握文件的读取/写入方法。
3. 掌握异常处理结构。

## 实验要求
1. 设计学生类；
2. 采用交互式方式实例化某学生；
3. 设计程序完成上述的业务逻辑处理，并且把“古诗处理后的输出”结果存储到学生基本信息所在的文本文件A中。
文件A包括两部分内容：

        一是学生的基本信息；
        二是学生处理后的作业信息，该作业的业务逻辑内容是：利用已学的字符串处理知识编程完成《长恨歌》古诗的整理对齐工作，写出功能方法
实现如下功能：

      1.每7个汉字加入一个标点符号，奇数时加“，”，偶数时加“。”
      2.允许提供输入参数，统计古诗中某个字或词出现的次数
      3.输入的文本来源于文本文件B读取，把处理好的结果写入到文本文件A
      4.考虑操作中可能出现的异常，在程序中设计异常处理程序

## 实验过程
### Student类
1. 在Student类中构造四个变量：String类型班级，String类型姓名，int类型学号，String类型性别；
2. 使用set（）方法和toString（）方法,返回相关对象的信息输出；
### Test类
1. 先使用Scanner进行交互输入,与Student.java关联
2. 将Student对象的学生信息存入A.txt中
3.读取B.txt中内容到BufferedReader中的in中,在对字符串进行分割
4.将学生信息和作业内容存入A.txt中
5. 设计一个查询,用for循环中设计switch查询字句,输出出现次数
6. 异常处理: 判断输入是否正确,文件是否存在,查询内容是否正确
## 核心代码
文件的读取写入

          BufferedReader in = new BufferedReader(new FileReader("D:\\B.txt"));
          String str = in.readLine();
 词句分割和标点处理
 
           String regex = "(.{7})";
                      str = str.replaceAll(regex,"$1，");
                      StringBuffer sb = new StringBuffer(str);
                      for (int i =15;i<240;i=i+17) {
                          sb.replace(i, i + 1, "。\n");
字词的查询

          Scanner c = new Scanner(System.in);
          String c1 = r.nextLine();
          int count = 0;
          int index = 0;
          while ((index = str.indexOf(c1, index)) != -1) {
              index = index + c1.length();
              count++;
          }

## 实验总结
通过这次实验,我对Java的异常处理机制的认识更清晰了.掌握了Scanner交互输入,文件的读取和写入.
对中文格式的输出错误也有了了解,对写一个完整的程序代码有了感悟.
