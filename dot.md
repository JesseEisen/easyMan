# dot

## rank

用来约束在子图中的节点，可以设置为`same` `min` `source` `max` `sink` 其中max对应着bottommost和rightmost而min对应着
leftmost和topmost。 same则是将节点放在同一个等级上。

    {rank=same; node1 node2 node3}

则上面的node1,node2,node3是处在同一个等级上的。

## nodesep

指定两个同等级的相邻的node之间的间隔，单位是inch。

## record

record的方向取决于rankdir的属性，如果是`TB`,`BT`(默认值)，则和垂直布局相对应的，record中的顶级字段是水平显示的。
如果是`LR`,`RL`则是水平显示，而文字则是竖直显示。

    node[shape=record]
    struct1[label="<f0> left|<f1> middle|<f2>right"];
    strucr2[label="<f0> one |<f1> two"];
    struct1:f0 -> struct2:f1;

## direction

    dir="forward"
    dir="back"

## arrow 

    arrowhead="none"
    arrowtail="normal"
    headlabel="1"
    taillabel="1.."
    arrowhead="diamond"

可以重新设置下arrow的样式


