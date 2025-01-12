---
id: 587d8256367417b2b2512c78
title: 隣接行列
challengeType: 1
forumTopicId: 301621
dashedName: adjacency-matrix
---

# --description--

グラフを表すもう一つの方法は、<dfn>隣接行列</dfn>に入れることです。 <dfn>隣接行列</dfn>は二次元 (2D) 配列で、入れ子になった各配列は外側の配列と同じ数の要素を持っています。 言い換えれば、数字の行列または格子であり、数字はエッジ (枝) を表します。

**注**: 行列の上と左の数字は、ノードの単なるラベルです。 行列内の 1 は、行と列を表す頂点 (ノード) の間にエッジが存在することを意味します。 最後に、0 はエッジ (関係) がないことを意味します。

<pre>
    1 2 3
  \------
1 | 0 1 1
2 | 1 0 0
3 | 1 0 0
</pre>

上記は非常にシンプルな無向グラフで、3 つのノードがあり、最初のノードが 2 番目と 3 番目のノードに接続されています。 下記は、同じことを JavaScript で実装したものです。

```js
var adjMat = [
  [0, 1, 1],
  [1, 0, 0],
  [1, 0, 0]
];
```

隣接リストとは異なり、行列の各「行」は、グラフ内のノードと同じ数の要素を持たなければなりません。 これは 3 × 3 の行列であり、つまりグラフに 3 つのノードがあります。 有向グラフもこれに似ています。 下のグラフでは、最初のノードは 2 番目のノードに向かうエッジを持ち、2 番目のノードは 3 番目のノードに向かうエッジを持っています。

```js
var adjMatDirected = [
  [0, 1, 0],
  [0, 0, 1],
  [0, 0, 0]
];
```

グラフのエッジに<dfn>重み</dfn>を付けることもできます。 これまでに見てきたエッジは、単にエッジの有無が二項 (`0` または `1`) で表された、<dfn>重み付けされていない</dfn>エッジです。 用途によって重みを変えることができます。

# --instructions--

5 つのノードを持つ無向グラフの隣接行列を作成してください。 この行列は多次元配列でなければなりません。 これら 5 つのノードは、1 番目と 4 番目のノード、1 番目と 3 番目のノード、3 番目と 5 番目のノード、および 4 番目と 5 番目のノードの間に関係があります。 エッジの重みはすべて 1 です。

# --hints--

`undirectedAdjList` には 5 つのノードのみが含まれている必要があります。

```js
assert(
  adjMatUndirected.length === 5 &&
    adjMatUndirected
      .map(function (x) {
        return x.length === 5;
      })
      .reduce(function (a, b) {
        return a && b;
      })
);
```

1 番目と 4 番目のノードの間にはエッジが必要です。

```js
assert(adjMatUndirected[0][3] === 1 && adjMatUndirected[3][0] === 1);
```

1 番目と 3 番目のノードの間にはエッジが必要です。

```js
assert(adjMatUndirected[0][2] === 1 && adjMatUndirected[2][0] === 1);
```

3 番目と 5 番目のノードの間にはエッジが必要です。

```js
assert(adjMatUndirected[2][4] === 1 && adjMatUndirected[4][2] === 1);
```

There should be an edge between the fourth and fifth node.

```js
assert(adjMatUndirected[3][4] === 1 && adjMatUndirected[4][3] === 1);
```

# --seed--

## --seed-contents--

```js
var adjMatUndirected = [];
```

# --solutions--

```js
var adjMatUndirected = [
  [0, 0, 1, 1, 0],
  [0, 0, 0, 0, 0],
  [1, 0, 0, 0, 1],
  [1, 0, 0, 0, 1],
  [0, 0, 1, 1, 0]
];
```
