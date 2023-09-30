# 数据结构!!!
## 链表
一个指向下\[上]一个元素的表
``` C++
struct Node{
  int data;
  Node *next=NULL,*pre=NULL;
}
void insert(Node* x,int s){  //在x后面插入d
  Node *d=new Node;
  d->data=s;
  x->next->pre=d;
  d->next=x->next;
  d->pre=x;
  x->next=d;
}
void deletes(Node *x){  //删除x
  x->pre->next=x->next;
  x->next->pre=x->pre;
  delete x;
}
```

## 栈
一个FILO(First in last out)的容器
``` C++
struct Stack{
  int *x,maxsize=-1,cnt=0;
  Stack(){
    x=new int[114];
    maxsize=114;
  }
  Stack(int size){
    x=new int[size];
    maxsize=size;
  }
  ~Stack(){
    delete []x;
  }
  void push(int s){
    if (cnt<maxsize) x[cnt++]=s;
  }
  int pop(){
    if (cnt>0)
    return x[--cnt];
  }
}
```

## 队列
## 简单树
### 二叉树
#### 遍历
#### 满二叉树
#### 哈夫曼
#### 二叉搜索
#### 
