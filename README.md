# byte-width
文字列のサイズをバイト数で計算する例題です。

### ``Substring``の単位テスト

```
  //start only

ASSERT("aあ"=TEXT_Get_substring_by_width ("aあ";0))
ASSERT("aあ"=TEXT_Get_substring_by_width ("aあ";1))
ASSERT(""=TEXT_Get_substring_by_width ("aあ";2))  //middle of あ; trim it
ASSERT(""=TEXT_Get_substring_by_width ("aあ";3))

ASSERT("あa"=TEXT_Get_substring_by_width ("あa";0))
ASSERT("あa"=TEXT_Get_substring_by_width ("あa";1))
ASSERT("a"=TEXT_Get_substring_by_width ("あa";2))  //middle of あ; trim it
ASSERT(""=TEXT_Get_substring_by_width ("あa";3))

  //start and length

  //start from 1
ASSERT(""=TEXT_Get_substring_by_width ("aあ";1;0))  //no length; return ""
ASSERT("a"=TEXT_Get_substring_by_width ("aあ";1;1))
ASSERT("a"=TEXT_Get_substring_by_width ("aあ";1;2))  //middle of あ; trim it
ASSERT("aあ"=TEXT_Get_substring_by_width ("aあ";1;3))  //return all
ASSERT("aあ"=TEXT_Get_substring_by_width ("aあ";1;4))  //overflow; return all

  //start from 2a
ASSERT(""=TEXT_Get_substring_by_width ("aあ";2;0))  //no length; return ""
ASSERT(""=TEXT_Get_substring_by_width ("aあ";2;1))  //middle of あ; trim it
ASSERT(""=TEXT_Get_substring_by_width ("aあ";2;2))  //middle of あ; trim it

  //start from 2b
ASSERT(""=TEXT_Get_substring_by_width ("あa";2;0))  //no length; return ""
ASSERT("a"=TEXT_Get_substring_by_width ("あa";2;1))
ASSERT("a"=TEXT_Get_substring_by_width ("あa";2;2))  //overflow; return all

  //start from 3
ASSERT(""=TEXT_Get_substring_by_width ("aあ";3;0))  //no length; return ""
ASSERT(""=TEXT_Get_substring_by_width ("aあ";3;1))  //overflow; return ""
```
