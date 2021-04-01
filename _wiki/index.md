---
layout  : wikiindex
title   : wiki
toc     : true
public  : true
comment : false
regenerate: true
---

## 등차 수열
[[Arithmetic_Sequence]]


[[Coding_Test_With_Python3-3]]

## arrayList
[[ArrayList]]


## index 
[[Mysql_index]]
## Object
[[object]]

## String
[[String]]


## 진수
[[digits]]

##
[[algorism_doit]]
## bigo
[[bigo]]
## static
[[static]]

## How to

- [[markdown]]

## Java

[[ArrayList]]


##
[[Terminal.md]]

## Variable

[[Variable]]

## Algorism1

[[algorism1]]
[[---]]

## Java Sort
[[java_sort]]

## blog posts
<div>
    <ul>
{% for post in site.posts %}
    {% if post.public != false %}
        <li>
            <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">
                {{ post.title }}
            </a>
        </li>
    {% endif %}
{% endfor %}
    </ul>
</div>

