---
layout: post
title: InsertSort
tag: DataStructure
---

**本系列所有文章均来自JS大神的日志**　[原文链接](http://user.qzone.qq.com/1033932438/blog/1390035575)

　　本人这两天复习了数据结构与算法，恰好看完了排序部分，觉得挺有趣，想在这里整理整理，跟有兴趣的读者分享分享。我将会对不同的排序算法分别用1篇日志来描述，以尽量做到思路清晰和描述详尽。对每个算法，我将会直接用1个例子来描述算法的基本思想，然后给出实现的代码，这些代码都经过了简单的测试。不过，代码可能还不能完全保证正确性，毕竟还是有待更多测试用例的考验，如果有读者发现代码有问题请及时通过评论提出来或者直接联系本人，本人将感激不尽！最后，我将会对每个算法分析其时间、空间复杂度，读者可以自行决定什么情况选择哪个排序算法最佳。另外，排序系列的日志将会陆续给出，并会不断进行修改哦~~。

　　首先让我们看看一些关于排序的概念。排序就是对某个含有n个元素的无序序列进行处理，这些元素假定是可以相互之间进行大小的比较，最终得出有序的序列。为了讨论的简单性，排序系列的日志均以int类型的元素为例，且序列使用数组存储，排序的结果是从小大大。根据不同的划分标准，排序算法可以有不同的种类。若根据存储被排序序列的场所划分，可分为内部排序和外部排序，内部排序就是序列的全部元素都存在内存里，外部排序则指序列的一部分位于内存，其余的在外部存储器上。简单起见，排序系列日志均只讨论内部排序；若根据排序的结果划分，可分为稳定排序和不稳定排序，例如，初始序列：49、38、65、97、76、13、27、49，49出现两次，用黑色表示第1个49，红色表示第2个49，以突出两者的相对顺序。若排序后，黑49仍在红49前，则该排序为稳定排序，否则为不稳定排序；若根据排序方法的不同来划分，则可分为5大类：插入排序、交换排序、选择排序、归并排序、基数排序。插入排序的具体种类有：直接插入排序、折半插入排序、2路插入排序、链表插入排序、希尔排序等；交换排序的具体种类有：冒泡排序、快速排序等；选择排序的具体种类有：简单选择排序、堆排序等。本人的排序系列日志正是根据以不同方法来划分的排序种类而展开的。

　　接下来，让我们看看第1个排序算法——直接插入排序。思想如下：假设初始序列仍为上述的： 49、38、65、97、76、13、27、49。从序列里直接取第1个元素49作为已有序部分，然后取第2个元素38，与已有序部分的最后那个元素49对比，38<49，则49向后移动1个位置，此时已有序部分已经到头，38便最终插入到49之前（49原来位置），此时序列为：38、49、65、97、76、13、27、49（蓝色代表已有序部分，以后同样如此表示）。接着取65，由于65与当前有序部分的末尾的49相比，65>49，则不需移动，65直接插入49后（即呆在原位不动），此时结果为：38、49、65、97、76、13、27、49。接着的97同理：38、49、65、97、76、13、27、49。然后76，76与已有序部分最后的97相比，76<97，则97需要向后移动1个位置，然后，76 > 65，则不再比较下去，76插入到65与97间（97原来的位置），此时结果为：38、49、65、76、97、13、27、49。接着13，13 < 97，97向后移动1个位置，13 < 76，76同样向后移动1个位置，如此下去，最后13<38，38向后移动1个位置后，13来到已有序部分的头部，不再进行比较，插入到38前（38原来的位置），结果为：13、38、49、65、76、97、27、49。接着27，27 < 97、27 < 76、……，这些元素顺次向后移动1个位置，最后发现，27 > 13，停止比较，27插入到13、38之间（38原来的位置），结果为：13、27、38、49、65、76、97、49。最后的49做同理的比较、移动操作，但最终会出现49=49，此时停止比较，49插入到49和65之间（65原来的位置），得：13、27、38、49、49、65、76、97。至此，处理完毕。

　　显然，直接插入排序属于稳定排序。代码如下： 

{% highlight c %}
void insertSort(int list[],int length)
{
    for(int i=1;i<length;++i)
    {
        int temp=list[i];
        int j;
        for(j=i-1;j>=0&&temp<list[j];--j) list[j+1]=list[j];
        list[j+1]=temp;
    }
}
{% endhighlight %}

　　设序列元素个数为n。从代码可看出，直接插入排序随元素个数改变而改变个数的操作主要是元素的比较与移动，而且一边进行比较一边进行移动，移动次数不多于比较次数，则时间复杂度的分析应看元素的比较次数。最好情况为初始序列完全顺序，此时，每趟排序只需比较1次，共n-1趟，则总比较次数为n-1；最坏情况为初始序列完全逆序，此时，第 i 趟排序需要比较 i 次，共n-1趟，则总比较次数为1+2+……+n-1=n（n-1）/ 2。综上，时间复杂度为O（n2） 。由于算法中没有使用随着元素个数改变而改变数量的辅助存储空间，则空间复杂度为O（1）。