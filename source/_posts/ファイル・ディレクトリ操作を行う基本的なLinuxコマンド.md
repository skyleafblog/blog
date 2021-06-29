---
title: ファイル・ディレクトリ操作を行う基本的なLinuxコマンド
date: 2021-06-08 00:00:00
tags:
---


<script type = "text/javascript" src = "https://ajax.googleapis.com/ajax/libs/jquery/1.9.1/jquery.min.js"></script>

<h1> ファイル・ディレクトリ操作を行う基本的なLinuxコマンド</h1>

<br>
<br>

<h2>1. Linuxを初めて扱うときの問題</h2>
<p>WindowsやMacでは、ファイルやフォルダの操作をグラフィック、マウスポインタなど視覚的かつ直感的なアプローチから行える。</p>
<p>一方Linuxでは、全ての操作をコマンドという文字の入力(以降「コマンド操作」)のみで実現しているため、初めて扱うときに戸惑う人が大半だと考えられる。</p>
<p>そこで、本記事では、コマンド操作をWindows、Macにおける従来の視覚的な表現とともに紹介することにより、いち早い理解を期待する。</p>
<p>まず初めに、ファイルやフォルダ(Linuxでは「ディレクトリ」)の操作を紹介する。</p>

<br>

<h2>2. ファイル・ディレクトリの操作</h2>

<p>本章では、なお、PCにサインインしているユーザ名は「User」とする。</p>
<p>また、エクスプローラーの「C:Users:User」を起点(ホームディレクトリ)として例を紹介する。</p>

<div class = "list1">2.1. pwd (print work directory)</div>

<div class = "listField">

 
</div>

<div class = "list2">2.2. cd (change directory)</div>

<div class = "listField">


</div>

<div class = "list3">2.3. mkdir (make directory)</div>

<div class = "listField">


</div>

<div class = "list4">2.4. ls (list)</div>

<div class = "listField">


</div>

<div class = "list5">2.5. mv (move)</div>

<div class = "listField">


</div>

<div class = "list6">2.6. cp (copy)</div>

<div class = "listField">


</div>

<div class = "list7">2.7. rm (remove)</div>

<div class = "listField">


</div>

<div class = "list8">2.8. file</div>

<div class = "listField">


</div>

次回３.ではコマンドの拡張的な使用法を紹介する。
## 3. オプションを使ったコマンドの拡張(工事中)

<script>

$(".listField").hide();

$(function(){

    $(document).ajaxStart(function (){
    
	    $.get("/pwd.txt");
    
    });

    $(document).ajaxError(function(event, XHR, set, ex){
    
        alert(ex);
    
    });
    
    $(".list1").click(function(){
    
        $.get("/pwd.txt", function(data,){
        
            $(".list1").next().html(data).slideToggle()
        
        });
    
    });
    
    $(".list2").click(function(){
    
        $.get("/cd.txt", function(data,){
        
            $(".list2").next().html(data).slideToggle()
        
        });
    
    });
    
    $(".list3").click(function(){
    
        $.get("/mkdir.txt", function(data,){
        
            $(".list3").next().html(data).slideToggle()
        
        });
    
    });
    
    $(".list4").click(function(){
    
        $.get("/ls.txt", function(data,){
        
            $(".list4").next().html(data).slideToggle()
        
        });
    
    });
    
    $(".list5").click(function(){
    
        $.get("/mv.txt", function(data,){
        
            $(".list5").next().html(data).slideToggle()
        
        });
    
    });
    
    $(".list6").click(function(){
    
        $.get("/cp.txt", function(data,){
        
            $(".list6").next().html(data).slideToggle()
        
        });
    
    });
    
    $(".list7").click(function(){
    
        $.get("/rm.txt", function(data,){
        
            $(".list7").next().html(data).slideToggle()
        
        });
    
    });
    
    $(".list8").click(function(){
    
        $.get("/file.txt", function(data,){
        
            $(".list8").next().html(data).slideToggle()
        
        });
    
    });

    $(".list1, .list2, .list3, .list4, .list5, .list6, .list7, .list8").hover(function (){
    
        $(this).css("backgroundColor", "lightgreen").css("color", "black");
        
    
    },function(){
    
        $(this).css("backgroundColor", "green").css("color", "white");
        
    
    });
    
    $(".list").hover(function() {
        $(this).next("span").animate({opacity: "show", top: "-75"}, "slow");}, function() {
      $(this).next("span").animate({opacity: "hide", top: "-85"}, "fast");
    });
    
});

</script>

<style type = "text/css">
    
    #inputField {
    
        background-color :#000000;
        color :#ffffff;
        width : 100%;
    
    }

    input {
    
        background-color :#000000;
        color :#ffffff;
        width : 97.5%;
        
    }
    
    p {
    
        font-family: "Arial", "メイリオ" ;
    
    }
    
    h1, h2, h3 {
    
        font-family: "MS Pゴシック" ;
        
    }
    
    .list1, .list2, .list3, .list4, .list5, .list6, .list7, .list8 {

        background-color: green;
        color : white;

        padding-top : 8px;
        padding-bottom : 8px;
        padding-left : 8px;
        margin-top : 4px;
        font-size : 18px
        
    
    }
    
    .listField {
    
        border-style: outset;
        padding-left : 8px;
        padding-right : 8px;
    
    }
    
    #example {
    
        border-style : ridge;
        padding-left : 8px;
    
    }

</style>