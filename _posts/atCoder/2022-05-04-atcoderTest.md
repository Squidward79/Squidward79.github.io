---
title: '[C#] 002 - Encyclopedia of Parentheses'
excerpt: AtCoder　競プロ典型 90問　002
categories:
  - atCoder
tags:
  - Coding Test

breadcrumb: true
---

<div class="notice--warning" markdown=1>
 <span>📄 難易度 : ⭐⭐⭐      </span>
 <span>📄 言語 : C#  </span>

 </div>

 [📂問題](https://atcoder.jp/contests/typical90/tasks/typical90_b)

***
##  🔶 解き方

### ✔ Bit Shiftを利用する

```cs
using System;
using System.Text;

namespace atCoder.Contest
{
    class Q_002_Encyclopedia_of_Parentheses
    {

        static void Main()
        {
            int N = Convert.ToInt32(Console.ReadLine());
            if (N % 2 == 1) return;

            // (1<<N)演算  == 2^N
            for (int i = 0; i < (1 << N); i++)
            {
                StringBuilder brackets = new StringBuilder();
                for (int j = N - 1; j > -1; j--)
                {
                    // i &(1<<j) は　iのj番目のビットを確認すること
                    if ((i & (1 << j)) == 0)
                        brackets.Append('(');
                    else
                        brackets.Append(')');
                }

                int count = 0;
                for (int k = 0; k < brackets.Length; k++)
                {
                    count += brackets[k] == '(' ? 1 : -1;
                    if (count < 0) break ;
                }

                if(count == 0)
                    Console.WriteLine(brackets);
            }
        }
    }
}
```

  <small style ="color:gray;">(post-code: categories_sub_01) </small>
 {: .text-right}

[TOP](#){: .btn .btn--warning}
{: .text-right}
