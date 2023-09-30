## 高精
别问了,直接上代码
``` C++
int _mod(int a,int b){
    if (b<=0) return -1;
    if (a>=0) return a%b;
    return b+(a-(a/b)*b);
struct bignum{
  char *x,size;
  bool f=0;
  bignum(int s){
    size=s;
    x=new char[s];
  }
  bignum(char *s){
    size=strlen(s);
    if (size==0){
        x=NULL;
        return;
    }
    if (s[0]=='-'){
      size--;
      f=1;
    }
    x=new char[size];
    for (int i=size-1;i>=0;i--){
      x[size-1-i]=s[i+f]-'0';
    }
  }
  bignum operator +(bignum s){
    int k=0,pos=0;
    bignum ret(max(size,s.size)+1);
    for (int i=0;i<ret.size-1;i++){
      if (i<size)
          if (f) k-=(x[i]-'0');
          else k+=(x[i]-'0');
      if (i<s.size)
          if (s.f)
            k-=s.x[i]-'0';
          else
            k+=s.x[i]-'0';
      ret.x[i]=_mod(k,10);
      k/=10;
    }
    if (k){
      ret.x[ret.size-1]=k;
      return ret;
    }
    ret.size--;
    return ret;
  void out(){
    if (f) printf("-");
    for (int i=size-1;i>=0;i--) printf("%d",x[i]);
  }
}
```
        
