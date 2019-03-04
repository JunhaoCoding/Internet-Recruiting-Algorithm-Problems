# ����2018У԰��Ƹ�㷨������

<!-- TOC -->
* [��һ��](#��һ��-�ַ���ƥ��)
* [�ڶ���](#�ڶ���-�������ƥ��)
* [������](#������-�ַ�����)
* [������](#������-���������)
<!-- TOC -->


## ��һ�� �ַ���ƥ��

### ��Ŀ����
>ţţ�������ַ���A��B,����A����һ��01��,B���г��˿�����0��1,��������'?',B�е�'?'����ȷ��Ϊ0����1�� Ѱ��һ���ַ���T�Ƿ����ַ���S�г��ֵĹ���,��Ϊ�ַ���ƥ�䡣ţţ���ڿ������п��ܵ��ַ���B,�ж����ֿ������ַ���A�����ƥ�䡣
����:A = "00010001", B = "??"
�ַ���B���ܵ��ַ�����"00","01","10","11",ֻ��"11"û�г������ַ���A��,�������3

**��������:**
>�����������,��һ��һ���ַ���A,�ַ���A����length(1 �� length �� 50),A��ÿ���ַ�����'0'����'1'��
 �ڶ���һ���ַ���B,�ַ���B����length(1 �� length �� 50),B�е��ַ�����'0','1'��'?'��

**�������:**
>���һ������,��ʾ�����ƥ����ַ���������

**������**
```
����
00010001
??
����
3
```

### ����˼·
- ��A�г��ȵ���B���ȵ����ַ����洢��HashSet�У�Ȼ����������������п��ܵ�B���ַ����洢��ArrayList,Ȼ���ж�ÿ�����ܵ��ַ����Ƿ���HashSet�С�

### �ο�����
```java
import java.util.ArrayList;
import java.util.HashSet;
import java.util.Scanner;

public class Main {

    public static void main(String[] args){
        Scanner in = new Scanner(System.in);
        String A = in.nextLine();
        String B = in.nextLine();
        ArrayList<String> possibleStringList = new ArrayList<>();
        int lenA = A.length();
        int lenB = B.length();
        int count = 0;
        HashSet<String> childStringOfA = new HashSet<>();
        for(int i=lenB;i<=lenA;i++){
            String str = A.substring(i-lenB,i);
            childStringOfA.add(str);
        }
        findPossibleString(B,"",0,lenB,possibleStringList);
        for(int i=0;i<possibleStringList.size();i++){
            if(childStringOfA.contains(possibleStringList.get(i)))
                count++;
        }
        System.out.println(count);
    }

    private static void findPossibleString(String str,String temp,int index,int len,ArrayList<String> stringList){
        if(index==len){
            stringList.add(temp);
            return;
        }
        if(str.charAt(index)=='?'){
            findPossibleString(str,temp+"0",index+1,len,stringList);
            findPossibleString(str,temp+"1",index+1,len,stringList);
        }else if(str.charAt(index)=='0'){
            findPossibleString(str,temp+"0",index+1,len,stringList);
        }else{
            findPossibleString(str,temp+"1",index+1,len,stringList);
        }
    }
}
```

## �ڶ��� �������ƥ��

### ��Ŀ����
>�Ϸ�������ƥ�����б�����Ϊ:
1. �մ�""�ǺϷ�����������
2. ���"X"��"Y"�ǺϷ�������,��ô"XY"Ҳ��һ���Ϸ�����������
3. ���"X"��һ���Ϸ�������,��ô"[X]"Ҳ��һ���Ϸ�����������
4. ÿ���Ϸ����������ж�����������Ĺ�������
����"", "[]", "[][][]", "[[][]]", "[[[[]]]]"���ǺϷ��ġ�
 ţţ���ڸ���һ����������s,ţţ������ִ�еĲ�����:��s�Ŀ�ʼ�ͽ�β�����һ��������������('[')����������(']')ʹ���Ϊһ���Ϸ�������ƥ�����С�ţţϣ���������������ٵ�����֮��ĺϷ�������ƥ��������ʲô��

**��������:**
>�������һ���ַ���s,s�ĳ���length(1 �� length �� 50),s��ֻ����`[`��`]`��

**�������:**
>���һ���ַ���,��ʾ������ȫƥ������С�

**������**
```
����
][

���
[][]
```

### ����˼·
- ������������left(��Ҫ�������ŵ�����)��right(��Ҫ�������ŵ�����)������`[`��right++������`]`��right--��left++��

### �ο�����
```java
import java.util.Scanner;
public class Main {
    public static void main(String[] args){
        Scanner in = new Scanner(System.in);
        String line = in.nextLine();
        if(line==null||line.length()==0) {
            System.out.println("");
            return;
        }
        char[] chars = line.toCharArray();
        int left=0;
        int right=0;
        for(int i=0;i<chars.length;i++){
            if(chars[i]=='['){
                right++;
            }else{
                if(right!=0)
                    right--;
                else
                    left++;
            }
        }
        String result = "";
        for(int i=0;i<left;i++){
            result+="[";
        }
        for(int i=0;i<chars.length;i++){
            result+=chars[i];
        }
        for(int i=0;i<right;i++){
            result+="]";
        }
        System.out.println(result);
    }
}
```

## ������ �ַ�����

### ��Ŀ����
>С����һ��Сд��ĸ��ɵ��ַ���s.�ַ���s�Ѿ���д��ǽ����.
 С�Ȼ��кܶ࿨Ƭ,ÿ����Ƭ����һ��Сд��ĸ,���һ���ַ���t��С�ȿ���ѡ���ַ���t������һ���ַ�,Ȼ�󸲸����ַ���s��һ���ַ�֮�ϡ�С����֪����ѡȡһЩ��Ƭ����s��һЩ�ַ�֮��,���Եõ����ֵ��������ַ�����ʲô��

**��������:**
>�����������,��һ��һ���ַ���s,�ַ���s����length(1 �� length �� 50),s��ÿ���ַ�����Сд��ĸ
 �ڶ���һ���ַ���t,�ַ���t����length(1 �� length �� 50),t��ÿ���ַ�����Сд��ĸ

**�������:**
>���һ���ַ���,�����Եõ����ֵ�������ַ���

**������**
```
����
fedcba
ee

���
feeeba
```

### ����˼·

- ѡ��t�������ַ���������������s�е��ַ��Ƚϣ��ҵ����Լ�С���滻��

### �ο�����

```java
import java.util.Arrays;
import java.util.Scanner;
public class Main {
    public static void main(String[] args){
        Scanner in = new Scanner(System.in);
        String s = in.nextLine();
        String t = in.nextLine();
        char[] sArr = s.toCharArray();
        char[] tArr = t.toCharArray();
        StringBuilder res = new StringBuilder();
        int index=tArr.length-1;
        Arrays.sort(tArr);
        for(int i=0;i<sArr.length;i++){
            if(index>=0){
                if(tArr[index]-sArr[i]>0){
                    res.append(tArr[index]);
                    index--;
                }else{
                    res.append(sArr[i]);
                }
            }
            else{
                res.append(sArr[i]);
            }
        }
        System.out.println(res.toString());
    }
}
```

## ������ ���������

### ��Ŀ����
>�����ַ���x��y, �������x�е�ĳЩ��ĸ(�п���ȫ�������߶�����)�ܹ��õ�y,���Ǿͳ�y��x�������С�����."ncd"��"nowcoder"��������,��"xt"���ǡ�
 ���ڶ��ڸ�����һ���ַ���s,�������ֵ�������s�������С� 

**��������:**
>�������һ��,һ���ַ���s,�ַ���s����length(1 �� length �� 50).
s��ÿ���ַ�����Сд��ĸ

**�������:**
>���һ���ַ���,���ֵ�������s�������С�

**������**
```
����
test

���
tt
```

### ����˼·

- ���ַ����е��ַ��������򣬴���������ȡ���ַ������ַ�˳�򲻱���Ӵ���

### �ο�����

```java
import java.util.Arrays;
import java.util.Comparator;
import java.util.Scanner;
public class Main {
    public static void main(String[] args){
        Scanner in = new Scanner(System.in);
        String s = in.nextLine();
        char[][] chars = new char[s.length()][2];
        for(int i=0;i<s.length();i++){
            chars[i][0]=s.charAt(i);
            chars[i][1]= (char) ('0'+i);
        }
        Arrays.sort(chars, new Comparator<char[]>() {
            @Override
            public int compare(char[] o1, char[] o2) {
                if(o1[0]-o2[0]==0) return o1[1]-o2[1];
                return o2[0]-o1[0];
            }
        });
        int index=-1;
        StringBuilder res = new StringBuilder();
        for(int i=0;i<s.length();i++){
            if(chars[i][1]-'0'>index){
                index=chars[i][1]-'0';
                res.append(chars[i][0]);
            }
        }
        System.out.println(res.toString());
    }
}
```
