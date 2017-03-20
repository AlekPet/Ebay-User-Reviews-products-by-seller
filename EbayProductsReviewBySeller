// ==UserScript==
// @name         eBAY Product reviews
// @namespace    http://tampermonkey.net/
// @version      0.1
// @description  Ebay check sellers
// @author       AlekPet 2017
// @match        http*://www.ebay.com/*
// @grant        none
// ==/UserScript==

(function() {
    var lang = 
    {
        ru:
        {
        otziv:"Отзывы о товаре",
        iskat:"Искать",
        },
        en:
        {
        otziv:"Product reviews",
        iskat:"Search",            
        }        
    };
    var yazik = lang.en;
    var sel_yz = "en";
    
    if(document.getElementsByClassName("gh-eb-Geo-txt")[0]){
       sel_yz = (document.getElementsByClassName("gh-eb-Geo-txt")[0].innerText == "Русский")?"ru":"en";  
    }
       yazik = (sel_yz == "ru")?lang.ru:lang.en; 
    
    var seller= document.getElementsByClassName("mbg-nw")[0].innerText;
    var tovar= (sel_yz == "ru")?document.getElementsByClassName("it-sttl")[0].dataset.mtdes:document.getElementById("itemTitle").innerHTML.replace('<span class="g-hdn">Details about  &nbsp;</span>','');

    var div = document.createElement("div");
    
    var past='<div style="margin:25px 0px;"><div style="font-size:12pt;color:#0bc60b;;">'+yazik.otziv+'</div>';
   past+='<div style="margin-top: 10px;"><input style="width: 60%; margin: 0; vertical-align: middle; background: linear-gradient(white,#78efef); border-radius: 5px; padding: 7px; color: #6b95a3; font-weight: bold;" class="notranslate MaxBidClass" id="inp_eb" value="'+tovar+'" title="Продавец: '+seller+'\nНазвание товара: '+tovar+'"><div onmouseover="this.style.background=&quot;linear-gradient(#5cf8fc, grey)&quot;;"  onmouseout="this.style.background=&quot;linear-gradient(black, silver)&quot;;"  style="cursor: pointer;    display: inline;    margin: 0 5px;    border: 1px solid;    padding: 5px;    background: linear-gradient(black,silver);    color: white;    font-weight: bold;" onclick="javascript:var seller=document.getElementsByClassName(\'mbg-nw\')[0].innerText;var tovar=this.parentElement.firstChild.value;window.open(&quot;http://www.feedbackselector.com/feedsearch.php?seller=&quot;+seller+&quot;&itemName=&quot;+tovar)">'+yazik.iskat+'</div></div></div>';
    div.innerHTML=past;
  document.getElementsByClassName("si-inner")[0].appendChild(div);
})();
