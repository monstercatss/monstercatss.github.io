# 书


<input type="checkbox" value="0" checked>奔跑吧梅洛斯<br />
<input type="checkbox" value="1">四叠半<br />
<input type="checkbox" value="2">灵山<br />
<input type="checkbox" value="3">规训与惩罚<br />
<input type="checkbox" value="4">疯癫与文明<br />

<script>
    
    //把第一个复选框设置未false，使用了jquery的索引
    $('input[type=checkbox]').eq(0).prop('checked', false)
    
    //所有都置为true，注意这里不能用attr，只能用prop
    $('input[type=checkbox]').prop('checked', true)
 
    //查询哪些被选中
    $('input[type=checkbox]').filter(':checked')
 
    //如果不用伪类就用循环，注意类数组不能用forEach
    function getValue(){
          const cbs =  $('input[type=checkbox]').toArray();
          let value = '';
          for(let i=0; i<cbs.length; i++){
 
              if($(cbs[i]).prop('checked')){
                  value += $(cbs[i]).val() + ','
              }
           }
           return value;
    }
  
</script>     




# 番
灵能百分百3<br />
孤独摇滚


# 音乐