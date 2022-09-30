---
id: megamenu
title: Megamenu
sidebar_label: Megamenu
---
A megamenu can divide your collection into different categories to make browsing easier. This example uses pre-formed search links based on subject headings, collection codes and shelving locations. Some categories also link to curated lists. Links are generated to sort by acquisition date and limited by copyright date so newest items are constantly at the top of the results.

## Sample
<html>
<ul id="browse-menu">
    <li class="dropdown">
        <span id="browse"><i class="fa fa-bars"></i>   BROWSE THE COLLECTION</span>
        <ul class="browse-vert-menu">
          <li>
            <a href="#">Books</a>
            <div class="dd-pullright">
                <div class="browse-row">
              <div class="browse-column">
                <h3>New Arrivals</h3>
                <ul>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=kw&op=and&idx=ti&op=and&idx=nb&limit=mc-ccode%3AAB&limit=mc-loc%3A120100ADNFB&limit=mc-loc%3A100100ADFICCF&limit=mc-loc%3A100200ADFIC&limit=mc-loc%3A100250ADFICGN&limit=mc-loc%3A100300ADFICHF&limit=mc-loc%3A100450ADFICHOL&limit=mc-loc%3A180100ADMAG&limit=mc-loc%3A100400ADFICM&limit=mc-loc%3A120200ADNF&limit=mc-loc%3A100500ADFICPBK&limit=mc-loc%3A100600ADFICPBKM&limit=mc-loc%3A100700ADFICPBKSF&limit=mc-loc%3A100800ADFICPBKW&limit=mc-loc%3A320440ADLPAD&limit=mc-loc%3A120300ADNFREF&limit=mc-loc%3A100850ADFICR&limit=mc-loc%3A100900ADFICSF&limit=mc-loc%3A120400ADNFTC&limit=mc-loc%3A101000ADFICW&limit=mc-loc%3A101100KFIC&limit=mc-loc%3A120700KNF&limit=mc-loc%3A340250NEW&limit-yr=2017-&sort_by=acqdate_dsc&do=Search">Regular Print</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=kw&op=and&idx=ti&op=and&idx=nb&limit=mc-ccode%3AAB&limit=mc-loc%3A120900LPNFB&limit=mc-loc%3A101200LPFICCF&limit=mc-loc%3A101300LPFIC&limit=mc-loc%3A101400LPFICM&limit=mc-loc%3A121000LPNF&limit=mc-loc%3A101500LPFICSF&limit=mc-loc%3A101600LPFICW&limit-yr=2017-&sort_by=acqdate_dsc&do=Search">Large Print</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=kw&op=and&idx=ti&op=and&idx=nb&do=Search&limit=mc-ccode%3AAUD&limit=mc-loc%3A260100ADAUDCAS&limit=mc-loc%3A260200ADAUDCD&limit=mc-loc%3A260250ADAUDMP3&limit=mc-loc%3A260300ADAUDPL&limit-yr=2017-&sort_by=acqdate_dsc&limit=">Audiobooks</a></li>
                </ul>
                <h3>Fiction</h3>
                <ul>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=Fantasy+fiction&op=and&idx=ti&op=and&idx=nb&do=Search&limit=mc-ccode%3AAB&limit=mc-ccode%3AAUD&limit=mc-loc%3A260100ADAUDCAS&limit=mc-loc%3A260200ADAUDCD&limit=mc-loc%3A260250ADAUDMP3&limit=mc-loc%3A260300ADAUDPL&limit=mc-loc%3A100100ADFICCF&limit=mc-loc%3A100200ADFIC&limit=mc-loc%3A100250ADFICGN&limit=mc-loc%3A100300ADFICHF&limit=mc-loc%3A100450ADFICHOL&limit=mc-loc%3A260350ADAUDMCAS&limit=mc-loc%3A100400ADFICM&limit=mc-loc%3A100500ADFICPBK&limit=mc-loc%3A100600ADFICPBKM&limit=mc-loc%3A100700ADFICPBKSF&limit=mc-loc%3A100800ADFICPBKW&limit=mc-loc%3A320440ADLPAD&limit=mc-loc%3A100850ADFICR&limit=mc-loc%3A100900ADFICSF&limit=mc-loc%3A220400ADVIDVHS&limit=mc-loc%3A101000ADFICW&limit=mc-loc%3A101100KFIC&limit=mc-loc%3A120700KNF&limit=mc-loc%3A101200LPFICCF&limit=mc-loc%3A101300LPFIC&limit=mc-loc%3A140800JUVFICLP&limit=mc-loc%3A101400LPFICM&limit=mc-loc%3A121000LPNF&sort_by=acqdate_dsc&limit=">Fantasy</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=Historical+fiction&op=and&idx=ti&op=and&idx=nb&do=Search&limit=mc-ccode%3AAB&limit=mc-ccode%3AAUD&limit=mc-loc%3A260100ADAUDCAS&limit=mc-loc%3A260200ADAUDCD&limit=mc-loc%3A260250ADAUDMP3&limit=mc-loc%3A260300ADAUDPL&limit=mc-loc%3A100100ADFICCF&limit=mc-loc%3A100200ADFIC&limit=mc-loc%3A100250ADFICGN&limit=mc-loc%3A100300ADFICHF&limit=mc-loc%3A100450ADFICHOL&limit=mc-loc%3A260350ADAUDMCAS&limit=mc-loc%3A100400ADFICM&limit=mc-loc%3A100500ADFICPBK&limit=mc-loc%3A100600ADFICPBKM&limit=mc-loc%3A100700ADFICPBKSF&limit=mc-loc%3A100800ADFICPBKW&limit=mc-loc%3A320440ADLPAD&limit=mc-loc%3A100850ADFICR&limit=mc-loc%3A100900ADFICSF&limit=mc-loc%3A220400ADVIDVHS&limit=mc-loc%3A101000ADFICW&limit=mc-loc%3A101100KFIC&limit=mc-loc%3A120700KNF&limit=mc-loc%3A101200LPFICCF&limit=mc-loc%3A101300LPFIC&limit=mc-loc%3A140800JUVFICLP&limit=mc-loc%3A101400LPFICM&limit=mc-loc%3A121000LPNF&sort_by=acqdate_dsc&limit=">Historical</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=Horror+fiction&op=and&idx=ti&op=and&idx=nb&do=Search&limit=mc-ccode%3AAB&limit=mc-ccode%3AAUD&limit=mc-loc%3A260100ADAUDCAS&limit=mc-loc%3A260200ADAUDCD&limit=mc-loc%3A260250ADAUDMP3&limit=mc-loc%3A260300ADAUDPL&limit=mc-loc%3A100100ADFICCF&limit=mc-loc%3A100200ADFIC&limit=mc-loc%3A100250ADFICGN&limit=mc-loc%3A100300ADFICHF&limit=mc-loc%3A100450ADFICHOL&limit=mc-loc%3A260350ADAUDMCAS&limit=mc-loc%3A100400ADFICM&limit=mc-loc%3A100500ADFICPBK&limit=mc-loc%3A100600ADFICPBKM&limit=mc-loc%3A100700ADFICPBKSF&limit=mc-loc%3A100800ADFICPBKW&limit=mc-loc%3A320440ADLPAD&limit=mc-loc%3A100850ADFICR&limit=mc-loc%3A100900ADFICSF&limit=mc-loc%3A220400ADVIDVHS&limit=mc-loc%3A101000ADFICW&limit=mc-loc%3A101100KFIC&limit=mc-loc%3A120700KNF&limit=mc-loc%3A101200LPFICCF&limit=mc-loc%3A101300LPFIC&limit=mc-loc%3A140800JUVFICLP&limit=mc-loc%3A101400LPFICM&limit=mc-loc%3A121000LPNF&sort_by=acqdate_dsc&limit=">Horror</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=Christian+fiction&op=and&idx=ti&op=and&idx=nb&do=Search&limit=mc-ccode%3AAB&limit=mc-ccode%3AAUD&limit=mc-loc%3A260100ADAUDCAS&limit=mc-loc%3A260200ADAUDCD&limit=mc-loc%3A260250ADAUDMP3&limit=mc-loc%3A260300ADAUDPL&limit=mc-loc%3A100100ADFICCF&limit=mc-loc%3A100200ADFIC&limit=mc-loc%3A100250ADFICGN&limit=mc-loc%3A100300ADFICHF&limit=mc-loc%3A100450ADFICHOL&limit=mc-loc%3A260350ADAUDMCAS&limit=mc-loc%3A100400ADFICM&limit=mc-loc%3A100500ADFICPBK&limit=mc-loc%3A100600ADFICPBKM&limit=mc-loc%3A100700ADFICPBKSF&limit=mc-loc%3A100800ADFICPBKW&limit=mc-loc%3A320440ADLPAD&limit=mc-loc%3A100850ADFICR&limit=mc-loc%3A100900ADFICSF&limit=mc-loc%3A220400ADVIDVHS&limit=mc-loc%3A101000ADFICW&limit=mc-loc%3A101100KFIC&limit=mc-loc%3A120700KNF&limit=mc-loc%3A101200LPFICCF&limit=mc-loc%3A101300LPFIC&limit=mc-loc%3A140800JUVFICLP&limit=mc-loc%3A101400LPFICM&limit=mc-loc%3A121000LPNF&sort_by=acqdate_dsc&limit=">Inspirational</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=Mystery+fiction&op=and&idx=ti&op=and&idx=nb&do=Search&limit=mc-ccode%3AAB&limit=mc-ccode%3AAUD&limit=mc-loc%3A260100ADAUDCAS&limit=mc-loc%3A260200ADAUDCD&limit=mc-loc%3A260250ADAUDMP3&limit=mc-loc%3A260300ADAUDPL&limit=mc-loc%3A100100ADFICCF&limit=mc-loc%3A100200ADFIC&limit=mc-loc%3A100250ADFICGN&limit=mc-loc%3A100300ADFICHF&limit=mc-loc%3A100450ADFICHOL&limit=mc-loc%3A260350ADAUDMCAS&limit=mc-loc%3A100400ADFICM&limit=mc-loc%3A100500ADFICPBK&limit=mc-loc%3A100600ADFICPBKM&limit=mc-loc%3A100700ADFICPBKSF&limit=mc-loc%3A100800ADFICPBKW&limit=mc-loc%3A320440ADLPAD&limit=mc-loc%3A100850ADFICR&limit=mc-loc%3A100900ADFICSF&limit=mc-loc%3A220400ADVIDVHS&limit=mc-loc%3A101000ADFICW&limit=mc-loc%3A101100KFIC&limit=mc-loc%3A120700KNF&limit=mc-loc%3A101200LPFICCF&limit=mc-loc%3A101300LPFIC&limit=mc-loc%3A140800JUVFICLP&limit=mc-loc%3A101400LPFICM&limit=mc-loc%3A121000LPNF&sort_by=acqdate_dsc&limit=">Mystery</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=Paranormal+fiction&op=and&idx=ti&op=and&idx=nb&do=Search&limit=mc-ccode%3AAB&limit=mc-ccode%3AAUD&limit=mc-loc%3A260100ADAUDCAS&limit=mc-loc%3A260200ADAUDCD&limit=mc-loc%3A260250ADAUDMP3&limit=mc-loc%3A260300ADAUDPL&limit=mc-loc%3A100100ADFICCF&limit=mc-loc%3A100200ADFIC&limit=mc-loc%3A100250ADFICGN&limit=mc-loc%3A100300ADFICHF&limit=mc-loc%3A100450ADFICHOL&limit=mc-loc%3A260350ADAUDMCAS&limit=mc-loc%3A100400ADFICM&limit=mc-loc%3A100500ADFICPBK&limit=mc-loc%3A100600ADFICPBKM&limit=mc-loc%3A100700ADFICPBKSF&limit=mc-loc%3A100800ADFICPBKW&limit=mc-loc%3A320440ADLPAD&limit=mc-loc%3A100850ADFICR&limit=mc-loc%3A100900ADFICSF&limit=mc-loc%3A220400ADVIDVHS&limit=mc-loc%3A101000ADFICW&limit=mc-loc%3A101100KFIC&limit=mc-loc%3A120700KNF&limit=mc-loc%3A101200LPFICCF&limit=mc-loc%3A101300LPFIC&limit=mc-loc%3A140800JUVFICLP&limit=mc-loc%3A101400LPFICM&limit=mc-loc%3A121000LPNF&sort_by=acqdate_dsc&limit=">Paranormal</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=Romance+fiction&op=and&idx=ti&op=and&idx=nb&do=Search&limit=mc-ccode%3AAB&limit=mc-ccode%3AAUD&limit=mc-loc%3A260100ADAUDCAS&limit=mc-loc%3A260200ADAUDCD&limit=mc-loc%3A260250ADAUDMP3&limit=mc-loc%3A260300ADAUDPL&limit=mc-loc%3A100100ADFICCF&limit=mc-loc%3A100200ADFIC&limit=mc-loc%3A100250ADFICGN&limit=mc-loc%3A100300ADFICHF&limit=mc-loc%3A100450ADFICHOL&limit=mc-loc%3A260350ADAUDMCAS&limit=mc-loc%3A100400ADFICM&limit=mc-loc%3A100500ADFICPBK&limit=mc-loc%3A100600ADFICPBKM&limit=mc-loc%3A100700ADFICPBKSF&limit=mc-loc%3A100800ADFICPBKW&limit=mc-loc%3A320440ADLPAD&limit=mc-loc%3A100850ADFICR&limit=mc-loc%3A100900ADFICSF&limit=mc-loc%3A220400ADVIDVHS&limit=mc-loc%3A101000ADFICW&limit=mc-loc%3A101100KFIC&limit=mc-loc%3A120700KNF&limit=mc-loc%3A101200LPFICCF&limit=mc-loc%3A101300LPFIC&limit=mc-loc%3A140800JUVFICLP&limit=mc-loc%3A101400LPFICM&limit=mc-loc%3A121000LPNF&sort_by=acqdate_dsc&limit=">Romance</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=Science+fiction&op=and&idx=ti&op=and&idx=nb&do=Search&limit=mc-ccode%3AAB&limit=mc-ccode%3AAUD&limit=mc-loc%3A260100ADAUDCAS&limit=mc-loc%3A260200ADAUDCD&limit=mc-loc%3A260250ADAUDMP3&limit=mc-loc%3A260300ADAUDPL&limit=mc-loc%3A100100ADFICCF&limit=mc-loc%3A100200ADFIC&limit=mc-loc%3A100250ADFICGN&limit=mc-loc%3A100300ADFICHF&limit=mc-loc%3A100450ADFICHOL&limit=mc-loc%3A260350ADAUDMCAS&limit=mc-loc%3A100400ADFICM&limit=mc-loc%3A100500ADFICPBK&limit=mc-loc%3A100600ADFICPBKM&limit=mc-loc%3A100700ADFICPBKSF&limit=mc-loc%3A100800ADFICPBKW&limit=mc-loc%3A320440ADLPAD&limit=mc-loc%3A100850ADFICR&limit=mc-loc%3A100900ADFICSF&limit=mc-loc%3A220400ADVIDVHS&limit=mc-loc%3A101000ADFICW&limit=mc-loc%3A101100KFIC&limit=mc-loc%3A120700KNF&limit=mc-loc%3A101200LPFICCF&limit=mc-loc%3A101300LPFIC&limit=mc-loc%3A140800JUVFICLP&limit=mc-loc%3A101400LPFICM&limit=mc-loc%3A121000LPNF&sort_by=acqdate_dsc&limit=">Science Fiction</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=suspense&op=and&idx=ti&op=and&idx=nb&do=Search&limit=mc-ccode%3AAB&limit=mc-ccode%3AAUD&limit=mc-loc%3A260100ADAUDCAS&limit=mc-loc%3A260200ADAUDCD&limit=mc-loc%3A260250ADAUDMP3&limit=mc-loc%3A260300ADAUDPL&limit=mc-loc%3A100100ADFICCF&limit=mc-loc%3A100200ADFIC&limit=mc-loc%3A100250ADFICGN&limit=mc-loc%3A100300ADFICHF&limit=mc-loc%3A100450ADFICHOL&limit=mc-loc%3A260350ADAUDMCAS&limit=mc-loc%3A100400ADFICM&limit=mc-loc%3A100500ADFICPBK&limit=mc-loc%3A100600ADFICPBKM&limit=mc-loc%3A100700ADFICPBKSF&limit=mc-loc%3A100800ADFICPBKW&limit=mc-loc%3A320440ADLPAD&limit=mc-loc%3A100850ADFICR&limit=mc-loc%3A100900ADFICSF&limit=mc-loc%3A220400ADVIDVHS&limit=mc-loc%3A101000ADFICW&limit=mc-loc%3A101100KFIC&limit=mc-loc%3A120700KNF&limit=mc-loc%3A101200LPFICCF&limit=mc-loc%3A101300LPFIC&limit=mc-loc%3A140800JUVFICLP&limit=mc-loc%3A101400LPFICM&limit=mc-loc%3A121000LPNF&sort_by=acqdate_dsc&limit=">Suspense</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=Western+fiction&op=and&idx=ti&op=and&idx=nb&do=Search&limit=mc-ccode%3AAB&limit=mc-ccode%3AAUD&limit=mc-loc%3A260100ADAUDCAS&limit=mc-loc%3A260200ADAUDCD&limit=mc-loc%3A260250ADAUDMP3&limit=mc-loc%3A260300ADAUDPL&limit=mc-loc%3A100100ADFICCF&limit=mc-loc%3A100200ADFIC&limit=mc-loc%3A100250ADFICGN&limit=mc-loc%3A100300ADFICHF&limit=mc-loc%3A100450ADFICHOL&limit=mc-loc%3A260350ADAUDMCAS&limit=mc-loc%3A100400ADFICM&limit=mc-loc%3A100500ADFICPBK&limit=mc-loc%3A100600ADFICPBKM&limit=mc-loc%3A100700ADFICPBKSF&limit=mc-loc%3A100800ADFICPBKW&limit=mc-loc%3A320440ADLPAD&limit=mc-loc%3A100850ADFICR&limit=mc-loc%3A100900ADFICSF&limit=mc-loc%3A220400ADVIDVHS&limit=mc-loc%3A101000ADFICW&limit=mc-loc%3A101100KFIC&limit=mc-loc%3A120700KNF&limit=mc-loc%3A101200LPFICCF&limit=mc-loc%3A101300LPFIC&limit=mc-loc%3A140800JUVFICLP&limit=mc-loc%3A101400LPFICM&limit=mc-loc%3A121000LPNF&sort_by=acqdate_dsc&limit=">Western</a></li>
                </ul>
              </div>
              <div class="browse-column">
                <h3>Nonfiction</h3>
                <ul>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=Biography&op=and&idx=ti&op=and&idx=nb&do=Search&limit=mc-ccode%3AAB&limit=mc-ccode%3AAUD&limit=mc-loc%3A260100ADAUDCAS&limit=mc-loc%3A260200ADAUDCD&limit=mc-loc%3A260250ADAUDMP3&limit=mc-loc%3A260300ADAUDPL&limit=mc-loc%3A120100ADNFB&limit=mc-loc%3A100100ADFICCF&limit=mc-loc%3A120200ADNF&limit=mc-loc%3A100700ADFICPBKSF&limit=mc-loc%3A120700KNF&limit=mc-loc%3A121000LPNF&limit=mc-loc%3A121200ADNFQ&sort_by=acqdate_dsc&limit=">Biography</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=Business&op=and&idx=ti&op=and&idx=nb&limit=mc-ccode%3AAB&limit=mc-ccode%3AAUD&limit=mc-loc%3A260100ADAUDCAS&limit=mc-loc%3A260200ADAUDCD&limit=mc-loc%3A260250ADAUDMP3&limit=mc-loc%3A260300ADAUDPL&limit=mc-loc%3A120100ADNFB&limit=mc-loc%3A100100ADFICCF&limit=mc-loc%3A120200ADNF&limit=mc-loc%3A100700ADFICPBKSF&limit=mc-loc%3A120700KNF&limit=mc-loc%3A121000LPNF&limit=mc-loc%3A121200ADNFQ&sort_by=acqdate_dsc">Business</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=Cooking&op=and&idx=ti&op=and&idx=nb&do=Search&limit=mc-ccode%3AAB&limit=mc-ccode%3AAUD&limit=mc-loc%3A260100ADAUDCAS&limit=mc-loc%3A260200ADAUDCD&limit=mc-loc%3A260250ADAUDMP3&limit=mc-loc%3A260300ADAUDPL&limit=mc-loc%3A120100ADNFB&limit=mc-loc%3A100100ADFICCF&limit=mc-loc%3A120200ADNF&limit=mc-loc%3A100700ADFICPBKSF&limit=mc-loc%3A120700KNF&limit=mc-loc%3A121000LPNF&limit=mc-loc%3A121200ADNFQ&sort_by=acqdate_dsc">Cooking</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=Crafts&op=or&idx=su%2Cwrdl&q=Hobbies&op=or&idx=su%2Cwrdl&do=Search&limit=mc-ccode%3AAB&limit=mc-ccode%3AAUD&limit=mc-loc%3A260100ADAUDCAS&limit=mc-loc%3A260200ADAUDCD&limit=mc-loc%3A260250ADAUDMP3&limit=mc-loc%3A260300ADAUDPL&limit=mc-loc%3A120100ADNFB&limit=mc-loc%3A100100ADFICCF&limit=mc-loc%3A120200ADNF&limit=mc-loc%3A100700ADFICPBKSF&limit=mc-loc%3A120700KNF&limit=mc-loc%3A121000LPNF&limit=mc-loc%3A121200ADNFQ&sort_by=acqdate_dsc">Crafts & Hobbies</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=callnum&q=616.&op=and&idx=ti&op=and&idx=nb&do=Search&limit=mc-ccode%3AAB&limit=mc-ccode%3AAUD&limit=mc-loc%3A260100ADAUDCAS&limit=mc-loc%3A260200ADAUDCD&limit=mc-loc%3A260250ADAUDMP3&limit=mc-loc%3A260300ADAUDPL&limit=mc-loc%3A120100ADNFB&limit=mc-loc%3A100100ADFICCF&limit=mc-loc%3A120200ADNF&limit=mc-loc%3A100700ADFICPBKSF&limit=mc-loc%3A120700KNF&limit=mc-loc%3A121000LPNF&limit=mc-loc%3A121200ADNFQ&sort_by=acqdate_dsc">Health & Wellness</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=history&op=and&idx=callnum&q=9*&op=not&idx=callnum&q=0*&op=not&idx=callnum&q=1*&op=not&idx=callnum&q=2*&op=not&idx=callnum&q=3*&op=not&idx=callnum&q=4*&op=not&idx=callnum&q=5*&op=not&idx=callnum&q=6*&op=not&idx=callnum&q=7*&op=not&idx=callnum&q=8*&op=not&idx=callnum&q=920.&do=Search&limit=mc-ccode%3AAB&limit=mc-loc%3A120200ADNF&limit=mc-loc%3A121000LPNF&sort_by=acqdate_dsc&limit=">History</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=callnum&q=500.&op=or&idx=callnum&q=510.&op=or&idx=callnum&q=5*&op=not&idx=callnum&q=0*&op=not&idx=callnum&q=1*&op=not&idx=callnum&q=2*&op=not&idx=callnum&q=3*&op=not&idx=callnum&q=4*&op=not&idx=callnum&q=6*&op=not&idx=callnum&q=7*&op=not&idx=callnum&q=8*&op=not&idx=callnum&q=9*&op=and&idx=kw&do=Search&limit=mc-ccode%3AAB&limit=mc-loc%3A120200ADNF&limit=mc-loc%3A121000LPNF&sort_by=acqdate_dsc&limit=">Math & Science</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=religion&op=and&idx=callnum&q=2*&op=and&idx=kw&do=Search&limit=mc-ccode%3AAB&limit=mc-loc%3A120200ADNF&limit=mc-loc%3A121000LPNF&sort_by=acqdate_dsc">Religion</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=callnum&q=796.&op=and&idx=su%2Cwrdl&q=sports&op=or&idx=su%2Cwrdl&q=Professional+sports&op=or&idx=su%2Cwrdl&q=baseball&op=or&idx=su%2Cwrdl&q=football&op=or&idx=su%2Cwrdl&q=soccer&op=or&idx=su%2Cwrdl&q=tennis&op=or&idx=su%2Cwrdl&q=hockey&op=or&idx=su%2Cwrdl&q=basketball&op=or&idx=su%2Cwrdl&q=racing&op=or&idx=su%2Cwrdl&q=wrestling&do=Search&limit=mc-ccode%3AAB&limit=mc-loc%3A120200ADNF&limit=mc-loc%3A121000LPNF&sort_by=acqdate_dsc">Sports</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=callnum&q=917.&op=and&idx=su%2Cwrdl&q=travel&limit=mc-ccode%3AAB&limit=mc-loc%3A120200ADNF&limit=mc-loc%3A121000LPNF&sort_by=acqdate_dsc">Travel</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=callnum&q=364.15&op=and&idx=callnum&do=Search&limit=mc-ccode%3AAB&limit=mc-loc%3A120200ADNF&limit=mc-loc%3A120400ADNFTC&limit=mc-loc%3A121000LPNF&sort_by=acqdate_dsc">True Crime</a></li>
                </ul>
              </div>
              <div class="browse-column">
                <ul>
                  <li class="browse-la-widget">
					<div class="libraryaware_widget_dc5322d12f5d4494b52fb19da7e1f1c0"></div>
                  </li>
                </ul>
              </div>
            </div>
          </li>
          <li>
            <a href="#">Movies & TV</a>
            <div class="dd-pullright">
              <div class="browse-column">
                <h3>New Arrivals</h3>
                <ul>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=films&op=and&idx=ti&op=and&idx=nb&do=Search&limit=mc-ccode%3ADVD&limit-yr=2017-&sort_by=acqdate_dsc">DVDs</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=films&op=and&idx=ti&op=and&idx=nb&do=Search&limit=mc-ccode%3ABLU&limit-yr=2017-&sort_by=acqdate_dsc">Blu-rays</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=television&op=and&idx=ti&op=and&idx=nb&do=Search&limit=mc-ccode%3ABLU&limit=mc-ccode%3ADVD&limit-yr=2017-&sort_by=acqdate_dsc">TV Series</a></li>
                </ul>
				<h3>Television</h3>
                <ul>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cphr&q=Action+and+adventure+television+programs&op=or&idx=su%2Cphr&do=Search&limit=mc-ccode%3ABLU&limit=mc-ccode%3ADVD&limit=mc-loc%3A220100ADVIDBLU&limit=mc-loc%3A220200ADVIDDVD&sort_by=acqdate_dsc">Action & Adventure</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cphr&q=Television+comedies&op=or&idx=su%2Cphr&do=Search&limit=mc-ccode%3ABLU&limit=mc-ccode%3ADVD&limit=mc-loc%3A220100ADVIDBLU&limit=mc-loc%3A220200ADVIDDVD&sort_by=acqdate_dsc">Comedies</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cphr&q=Television+crime+shows&op=or&idx=su%2Cphr&do=Search&limit=mc-ccode%3ABLU&limit=mc-ccode%3ADVD&limit=mc-loc%3A220100ADVIDBLU&limit=mc-loc%3A220200ADVIDDVD&sort_by=acqdate_dsc">Crime</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cphr&q=Documentary+television+programs&op=or&idx=su%2Cphr&do=Search&limit=mc-ccode%3ABLU&limit=mc-ccode%3ADVD&limit=mc-loc%3A220100ADVIDBLU&limit=mc-loc%3A220200ADVIDDVD&sort_by=acqdate_dsc">Documentaries</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cphr&q=Horror+television+programs&op=or&idx=su%2Cphr&do=Search&limit=mc-ccode%3ABLU&limit=mc-ccode%3ADVD&limit=mc-loc%3A220100ADVIDBLU&limit=mc-loc%3A220200ADVIDDVD&sort_by=acqdate_dsc">Horror</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cphr&q=Reality+television+programs&op=or&idx=su%2Cphr&do=Search&limit=mc-ccode%3ABLU&limit=mc-ccode%3ADVD&limit=mc-loc%3A220100ADVIDBLU&limit=mc-loc%3A220200ADVIDDVD&sort_by=acqdate_dsc">Reality TV</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cphr&q=Science+fiction+television+programs&op=or&idx=su%2Cphr&q=Fantasy+television+programs&do=Search&limit=mc-ccode%3ABLU&limit=mc-ccode%3ADVD&limit=mc-loc%3A220100ADVIDBLU&limit=mc-loc%3A220200ADVIDDVD&sort_by=acqdate_dsc">Sci-Fi & Fantasy</a></li>
                </ul>
              </div>
              <div class="browse-column">
                <h3>Movies</h3>
                <ul>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=Action+and+adventure+films&limit=mc-ccode%3A'BLU'&limit=mc-ccode%3A'DVD'&limit=mc-loc%3A'220100ADVIDBLU'&limit=mc-loc%3A'220200ADVIDDVD'&sort_by=acqdate_dsc">Action & Adventure</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=Animated+films&op=or&idx=su%2Cwrdl&do=Search&limit=mc-ccode%3ABLU&limit=mc-ccode%3ADVD&limit=mc-loc%3A220100ADVIDBLU&limit=mc-loc%3A220200ADVIDDVD&sort_by=acqdate_dsc">Animated</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cphr&q=comedy+films&op=or&idx=su%2Cwrdl&do=Search&limit=mc-ccode%3ABLU&limit=mc-ccode%3ADVD&limit=mc-loc%3A220100ADVIDBLU&limit=mc-loc%3A220200ADVIDDVD&sort_by=acqdate_dsc">Comedies</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cphr&q=documentary+films&op=or&idx=su%2Cwrdl&do=Search&limit=mc-ccode%3ABLU&limit=mc-ccode%3ADVD&limit=mc-loc%3A220100ADVIDBLU&limit=mc-loc%3A220200ADVIDDVD&sort_by=acqdate_dsc">Documentaries</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=drama+film&op=or&idx=su%2Cwrdl&do=Search&limit=mc-ccode%3ABLU&limit=mc-ccode%3ADVD&limit=mc-loc%3A220100ADVIDBLU&limit=mc-loc%3A220200ADVIDDVD&sort_by=acqdate_dsc">Dramas</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cphr&q=horror+films&op=or&idx=su%2Cwrdl&do=Search&limit=mc-ccode%3ABLU&limit=mc-ccode%3ADVD&limit=mc-loc%3A220100ADVIDBLU&limit=mc-loc%3A220200ADVIDDVD&sort_by=acqdate_dsc">Horror</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cphr&q=musical+films&op=or&idx=su%2Cwrdl&do=Search&limit=mc-ccode%3ABLU&limit=mc-ccode%3ADVD&limit=mc-loc%3A220100ADVIDBLU&limit=mc-loc%3A220200ADVIDDVD&sort_by=acqdate_dsc">Musicals</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cphr&q=science+fiction+films&op=or&idx=su%2Cphr&q=fantasy+films&do=Search&limit=mc-ccode%3ABLU&limit=mc-ccode%3ADVD&limit=mc-loc%3A220100ADVIDBLU&limit=mc-loc%3A220200ADVIDDVD&sort_by=acqdate_dsc">Sci-Fi & Fantasy</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cphr&q=Thrillers+(Motion+pictures)&op=or&idx=su%2Cphr&do=Search&limit=mc-ccode%3ABLU&limit=mc-ccode%3ADVD&limit=mc-loc%3A220100ADVIDBLU&limit=mc-loc%3A220200ADVIDDVD&sort_by=acqdate_dsc">Thrillers</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cphr&q=western+films&op=or&idx=su%2Cphr&do=Search&limit=mc-ccode%3ABLU&limit=mc-ccode%3ADVD&limit=mc-loc%3A220100ADVIDBLU&limit=mc-loc%3A220200ADVIDDVD&sort_by=acqdate_dsc">Westerns</a></li>
                </ul>
              </div>
              <div class="browse-column">
              </div>
            </div>
          </li>
          <li>
            <a href="#">Teens</a>
            <div class="dd-pullright">
              <div class="browse-column">
                <h3>New Arrivals</h3>
                <ul>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=kw&op=and&idx=ti&op=and&idx=nb&limit=mc-loc%3A101800YAFIC&limit=mc-loc%3A102000YAFICPBKF&limit=mc-loc%3A102100YAFICSF&limit-yr=2017-&sort_by=acqdate_dsc">Fiction</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=kw&op=and&idx=ti&op=and&idx=nb&limit=mc-loc%3A121600YANFB&limit=mc-loc%3A121700YANF&limit-yr=2017-&sort_by=acqdate_dsc">Nonfiction</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=kw&op=and&idx=ti&op=and&idx=nb&limit=mc-loc%3A101900YAFICGN&limit-yr=2017-&sort_by=acqdate_dsc">Graphic Novels</a></li>
                </ul>
                <h3>Graphic novels</h3>
                <ul>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=adventure&op=or&idx=su%2Cwrdl&q=adventurers&op=or&idx=su%2Cwrdl&q=adventures&limit=mc-loc%3A'100250ADFICGN'&limit=mc-loc%3A'101900YAFICGN'&offset=0&sort_by=acqdate_dsc">Adventure</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=magic&op=+or+&idx=su%2Cwrdl&q=fantasy&op=+or+&idx=nb&q=hero&limit=mc-loc%3A'100250ADFICGN'&limit=mc-loc%3A'101900YAFICGN'&sort_by=acqdate_dsc">Fantasy</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=horror&op=and&idx=ti&op=and&idx=nb&do=Search&limit=mc-loc%3A101900YAFICGN&sort_by=acqdate_dsc">Horror</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=kw&q=manga&op=and&idx=ti&op=and&idx=nb&do=Search&limit=mc-loc%3A101900YAFICGN&sort_by=acqdate_dsc">Manga</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=science+fiction&op=and&idx=ti&op=and&idx=nb&do=Search&limit=mc-loc%3A101900YAFICGN&sort_by=acqdate_dsc">Science Fiction</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=heroes&op=or&idx=su%2Cwrdl&q=superheroes&op=or&idx=su%2Cwrdl&q=hero&op=or&idx=su%2Cwrdl&q=superhero&limit=mc-loc%3A'100250ADFICGN'&limit=mc-loc%3A'101900YAFICGN'&offset=0&sort_by=acqdate_dsc">Heroes & Superheroes</a></li>
                </ul>
              </div>
              <div class="browse-column">
                <h3>Browse</h3>
                <ul>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=Adventure&op=+or+&idx=su%2Cwrdl&q=Adventurers&op=+or+&idx=su%2Cwrdl&q=Survival&limit=mc-loc%3A'260500YAAUDCAS'&limit=mc-loc%3A'260600YAAUDCD'&limit=mc-loc%3A'121600YANFB'&limit=mc-loc%3A'101800YAFIC'&limit=mc-loc%3A'121700YANF'&limit=mc-loc%3A'102000YAFICPBKF'&limit=mc-loc%3A'102100YAFICSF'&sort_by=acqdate_dsc">Adventure & Survival</a></li>
                  <li><a href="/cgi-bin/koha/opac-shelves.pl?op=view&shelfnumber=2963&sortfield=title">Books to Movies</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=Fantasy&op=+or+&idx=su%2Cwrdl&q=Magic&op=+or+&idx=su%2Cwrdl&q=Wizards&limit=mc-loc%3A'260500YAAUDCAS'&limit=mc-loc%3A'260600YAAUDCD'&limit=mc-loc%3A'121600YANFB'&limit=mc-loc%3A'101800YAFIC'&limit=mc-loc%3A'121700YANF'&limit=mc-loc%3A'102000YAFICPBKF'&limit=mc-loc%3A'102100YAFICSF'&sort_by=acqdate_dsc">Fantasy</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=Horror&limit=mc-loc%3A'260500YAAUDCAS'&limit=mc-loc%3A'260600YAAUDCD'&limit=mc-loc%3A'121600YANFB'&limit=mc-loc%3A'101800YAFIC'&limit=mc-loc%3A'121700YANF'&limit=mc-loc%3A'102000YAFICPBKF'&limit=mc-loc%3A'102100YAFICSF'&sort_by=acqdate_dsc">Horror</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=Mystery&op=+or+&idx=su%2Cwrdl&q=Crime&op=+or+&idx=su%2Cwrdl&q=Criminal&op=+or+&idx=su%2Cwrdl&q=Detective&op=+or+&idx=su%2Cwrdl&q=Murder&limit=mc-loc%3A'260500YAAUDCAS'&limit=mc-loc%3A'260600YAAUDCD'&limit=mc-loc%3A'121600YANFB'&limit=mc-loc%3A'101800YAFIC'&limit=mc-loc%3A'121700YANF'&limit=mc-loc%3A'102000YAFICPBKF'&limit=mc-loc%3A'102100YAFICSF'&sort_by=acqdate_dsc">Murder & Mystery</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=Romance&op=or&idx=su%2Cwrdl&q=Love&op=or&idx=su%2Cwrdl&q=Man-woman+relationships&op=or&idx=su%2Cwrdl&q=Dating&do=Search&limit=mc-loc%3A260500YAAUDCAS&limit=mc-loc%3A260600YAAUDCD&limit=mc-loc%3A121600YANFB&limit=mc-loc%3A101800YAFIC&limit=mc-loc%3A121700YANF&limit=mc-loc%3A102000YAFICPBKF&limit=mc-loc%3A102100YAFICSF&sort_by=acqdate_dsc">Romance</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=science+fiction&op=or&idx=su%2Cwrdl&q=time+travel&do=Search&limit=mc-loc%3A260500YAAUDCAS&limit=mc-loc%3A260600YAAUDCD&limit=mc-loc%3A121600YANFB&limit=mc-loc%3A101800YAFIC&limit=mc-loc%3A121700YANF&limit=mc-loc%3A102000YAFICPBKF&limit=mc-loc%3A102100YAFICSF&sort_by=acqdate_dsc">Sci-Fi</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=sports&op=or&idx=su%2Cwrdl&q=baseball&op=or&idx=su%2Cwrdl&q=basketball&op=or&idx=su%2Cwrdl&q=boxing&op=or&idx=su%2Cwrdl&q=football&op=or&idx=su%2Cwrdl&q=soccer&do=Search&limit=mc-loc%3A260500YAAUDCAS&limit=mc-loc%3A260600YAAUDCD&limit=mc-loc%3A121600YANFB&limit=mc-loc%3A101800YAFIC&limit=mc-loc%3A121700YANF&limit=mc-loc%3A102000YAFICPBKF&limit=mc-loc%3A102100YAFICSF&sort_by=acqdate_dsc">Sports</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=supernatural&op=or&idx=su%2Cwrdl&q=ghosts&op=or&idx=su%2Cwrdl&q=haunted&op=or&idx=su%2Cwrdl&q=monsters&op=or&idx=su%2Cwrdl&q=paranormal&op=or&idx=su%2Cwrdl&q=vampires&op=or&idx=su%2Cwrdl&q=werewolves&op=or&idx=su%2Cwrdl&q=zombies&do=Search&limit=mc-loc%3A260500YAAUDCAS&limit=mc-loc%3A260600YAAUDCD&limit=mc-loc%3A121600YANFB&limit=mc-loc%3A101800YAFIC&limit=mc-loc%3A121700YANF&limit=mc-loc%3A102000YAFICPBKF&limit=mc-loc%3A102100YAFICSF&sort_by=acqdate_dsc">Supernatural</a></li>
                </ul>
              </div>
              <div class="browse-column">
                <ul>
                  <li class="browse-la-widget">
					<div class="libraryaware_widget_408cccb202ea4819a44481fc0b117649"></div>
                  </li>
                </ul>
              </div>
            </div>
          </li>    
          <li>
            <a href="#">Kids</a>
            <div class="dd-pullright">
              <div class="browse-column">
                <h3>New Arrivals</h3>
                <ul>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=kw&op=and&idx=ti&op=and&idx=nb&limit=mc-ccode%3AJB&limit=mc-loc%3A140100JUVFICBR&limit=mc-loc%3A140200JUVFICBB&limit=mc-loc%3A140350JUVFICCHI&limit=mc-loc%3A140450JUVFICP&limit-yr=2017-&sort_by=acqdate_dsc">Picture Books & Early Readers</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=kw&op=and&idx=ti&op=and&idx=nb&limit=mc-ccode%3AJB&limit=mc-loc%3A140325JUVFICBC&limit=mc-loc%3A140500JUVFIC&limit-yr=2017-&sort_by=acqdate_dsc">Chapter Books</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=kw&op=and&idx=ti&op=and&idx=nb&limit=mc-ccode%3AJB&limit=mc-loc%3A140600JUVFICGN&limit-yr=2017-&sort_by=acqdate_dsc">Graphic Novels</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=kw&op=and&idx=ti&op=and&idx=nb&limit=mc-ccode%3AJB&limit=mc-loc%3A160200JUVNF&limit=mc-loc%3A160300JUVNFREF&limit-yr=2017-&sort_by=acqdate_dsc">Non-Fiction</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=kw&op=and&idx=ti&op=and&idx=nb&limit=mc-loc%3A280100JUVAUDBAC&limit=mc-loc%3A280200JUVAUDCAS&limit=mc-loc%3A280300JUVAUDCD&limit=mc-loc%3A280400JUVAUDPL&limit-yr=2017-&sort_by=acqdate_dsc">Audiobooks</a></li>
                </ul>
                <h3>Popular Series</h3>
                <ul>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=ti&q=bad+kitty&op=and&idx=au%2Cwrdl&q=bruel&op=and&idx=nb&do=Search&sort_by=pubdate_dsc">Bad Kitty</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=ti&q=big+nate&op=and&idx=au%2Cwrdl&q=peirce&op=and&idx=nb&do=Search&sort_by=pubdate_dsc">Big Nate</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=ti%2Cphr&q=Diary+of+a+wimpy+kid&op=and&idx=ti&op=and&idx=nb&sort_by=pubdate_dsc">Diary of a Wimpy Kid</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=ti&q=dog+man&op=and&idx=au%2Cwrdl&q=pilkey&op=and&idx=nb&do=Search&sort_by=pubdate_dsc">Dog Man</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=ti&q=dork+diaries&op=and&idx=au%2Cwrdl&q=russell&op=and&idx=nb&do=Search&sort_by=pubdate_dsc">Dork Diaries</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=ti&q=Harry+Potter&op=and&idx=au%2Cwrdl&q=rowling&op=and&idx=nb&do=Search&sort_by=pubdate_dsc">Harry Potter</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=ti&q=i+survived&op=and&idx=au%2Cwrdl&q=tarshis&op=and&idx=nb&do=Search&sort_by=pubdate_dsc">I Survived...</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=ti&q=Magic+Tree+House&op=and&idx=au%2Cwrdl&q=osborne&op=and&idx=nb&do=Search&sort_by=pubdate_dsc">Magic Tree House</a></li>
                </ul>
              </div>
              <div class="browse-column">
                <h3>Nonfiction</h3>
                <ul>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=animals&op=or&idx=su%2Cwrdl&q=wildlife&op=or&idx=su%2Cwrdl&q=pets&do=Search&limit=mc-loc%3A160200JUVNF&sort_by=acqdate_dsc">Animals</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=handicraft&op=or&idx=su%2Cwrdl&q=crafts&op=or&idx=su%2Cwrdl&q=drawing&op=or&idx=su%2Cwrdl&do=Search&limit=mc-loc%3A160100JUVNFB&limit=mc-loc%3A160200JUVNF&sort_by=acqdate_dsc">Arts & Crafts</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=Biography&op=and&idx=ti&do=Search&limit=mc-loc%3A160100JUVNFB&limit=mc-loc%3A160200JUVNF&sort_by=acqdate_dsc">Biographies</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=automobiles&op=or&idx=su%2Cwrdl&q=trains&op=or&idx=su%2Cwrdl&q=transportation&op=or&idx=su%2Cwrdl&q=construction+equipment&op=or&idx=su%2Cwrdl&q=vehicles&do=Search&limit=mc-loc%3A160200JUVNF&sort_by=acqdate_dsc">Cars, Trains & More</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=cooking&op=and&idx=kw&do=Search&limit=mc-loc%3A160200JUVNF&sort_by=acqdate_dsc">Cooking</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=fairy+tales&op=and&idx=kw&do=Search&limit=mc-loc%3A160200JUVNF&sort_by=acqdate_dsc">Fairy Tales</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=geography&op=and&idx=kw&do=Search&limit=mc-loc%3A160200JUVNF&sort_by=acqdate_dsc">Geography</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=history&op=and&idx=callnum&q=900&do=Search&limit=mc-loc%3A160200JUVNF&sort_by=acqdate_dsc">History</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=science&op=and&idx=callnum&q=500&do=Search&limit=mc-loc%3A160200JUVNF&sort_by=acqdate_dsc">Science</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=sports&op=and&idx=ti&op=and&idx=nb&limit=mc-loc%3A160100JUVNFB&limit=mc-loc%3A160200JUVNF&sort_by=acqdate_dsc">Sports</a></li>
                </ul>
                <h3>Movies & TV</h3>
                <ul>
                  <li><a href="/cgi-bin/koha/opac-search.pl?&do=Search&limit=mc-loc%3A240200JUVVIDDVD&sort_by=acqdate_dsc">DVDs</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?&do=Search&limit=mc-loc%3A240100JUVVIDBLU&sort_by=acqdate_dsc">Blu-rays</a></li>
                  <li><a href="/cgi-bin/koha/opac-shelves.pl?op=view&shelfnumber=2962&sortfield=title">Books to Movies</a></li>
                </ul>
              </div>
              <div class="browse-column">
                <ul>
                  <li class="browse-la-widget">
					<div class="libraryaware_widget_22f3d77f1859469c916da2fe7f637026"></div>
                  </li>
                </ul>
              </div>
            </div>
          </li>
        </ul>
      </li>
    </ul>
</html>

## HTML
```html
      <ul id="browse-menu">
      <li class="dropdown">
        <span id="browse"><i class="fa fa-bars"></i>   BROWSE THE COLLECTION</span>
        <ul class="browse-vert-menu">
          <li>
            <a href="#">Books</a>
            <div class="dd-pullright">
                <div class="browse-row">
              <div class="browse-column">
                <h3>New Arrivals</h3>
                <ul>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=kw&op=and&idx=ti&op=and&idx=nb&limit=mc-ccode%3AAB&limit=mc-loc%3A120100ADNFB&limit=mc-loc%3A100100ADFICCF&limit=mc-loc%3A100200ADFIC&limit=mc-loc%3A100250ADFICGN&limit=mc-loc%3A100300ADFICHF&limit=mc-loc%3A100450ADFICHOL&limit=mc-loc%3A180100ADMAG&limit=mc-loc%3A100400ADFICM&limit=mc-loc%3A120200ADNF&limit=mc-loc%3A100500ADFICPBK&limit=mc-loc%3A100600ADFICPBKM&limit=mc-loc%3A100700ADFICPBKSF&limit=mc-loc%3A100800ADFICPBKW&limit=mc-loc%3A320440ADLPAD&limit=mc-loc%3A120300ADNFREF&limit=mc-loc%3A100850ADFICR&limit=mc-loc%3A100900ADFICSF&limit=mc-loc%3A120400ADNFTC&limit=mc-loc%3A101000ADFICW&limit=mc-loc%3A101100KFIC&limit=mc-loc%3A120700KNF&limit=mc-loc%3A340250NEW&limit-yr=2017-&sort_by=acqdate_dsc&do=Search">Regular Print</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=kw&op=and&idx=ti&op=and&idx=nb&limit=mc-ccode%3AAB&limit=mc-loc%3A120900LPNFB&limit=mc-loc%3A101200LPFICCF&limit=mc-loc%3A101300LPFIC&limit=mc-loc%3A101400LPFICM&limit=mc-loc%3A121000LPNF&limit=mc-loc%3A101500LPFICSF&limit=mc-loc%3A101600LPFICW&limit-yr=2017-&sort_by=acqdate_dsc&do=Search">Large Print</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=kw&op=and&idx=ti&op=and&idx=nb&do=Search&limit=mc-ccode%3AAUD&limit=mc-loc%3A260100ADAUDCAS&limit=mc-loc%3A260200ADAUDCD&limit=mc-loc%3A260250ADAUDMP3&limit=mc-loc%3A260300ADAUDPL&limit-yr=2017-&sort_by=acqdate_dsc&limit=">Audiobooks</a></li>
                </ul>
                <h3>Fiction</h3>
                <ul>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=Fantasy+fiction&op=and&idx=ti&op=and&idx=nb&do=Search&limit=mc-ccode%3AAB&limit=mc-ccode%3AAUD&limit=mc-loc%3A260100ADAUDCAS&limit=mc-loc%3A260200ADAUDCD&limit=mc-loc%3A260250ADAUDMP3&limit=mc-loc%3A260300ADAUDPL&limit=mc-loc%3A100100ADFICCF&limit=mc-loc%3A100200ADFIC&limit=mc-loc%3A100250ADFICGN&limit=mc-loc%3A100300ADFICHF&limit=mc-loc%3A100450ADFICHOL&limit=mc-loc%3A260350ADAUDMCAS&limit=mc-loc%3A100400ADFICM&limit=mc-loc%3A100500ADFICPBK&limit=mc-loc%3A100600ADFICPBKM&limit=mc-loc%3A100700ADFICPBKSF&limit=mc-loc%3A100800ADFICPBKW&limit=mc-loc%3A320440ADLPAD&limit=mc-loc%3A100850ADFICR&limit=mc-loc%3A100900ADFICSF&limit=mc-loc%3A220400ADVIDVHS&limit=mc-loc%3A101000ADFICW&limit=mc-loc%3A101100KFIC&limit=mc-loc%3A120700KNF&limit=mc-loc%3A101200LPFICCF&limit=mc-loc%3A101300LPFIC&limit=mc-loc%3A140800JUVFICLP&limit=mc-loc%3A101400LPFICM&limit=mc-loc%3A121000LPNF&sort_by=acqdate_dsc&limit=">Fantasy</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=Historical+fiction&op=and&idx=ti&op=and&idx=nb&do=Search&limit=mc-ccode%3AAB&limit=mc-ccode%3AAUD&limit=mc-loc%3A260100ADAUDCAS&limit=mc-loc%3A260200ADAUDCD&limit=mc-loc%3A260250ADAUDMP3&limit=mc-loc%3A260300ADAUDPL&limit=mc-loc%3A100100ADFICCF&limit=mc-loc%3A100200ADFIC&limit=mc-loc%3A100250ADFICGN&limit=mc-loc%3A100300ADFICHF&limit=mc-loc%3A100450ADFICHOL&limit=mc-loc%3A260350ADAUDMCAS&limit=mc-loc%3A100400ADFICM&limit=mc-loc%3A100500ADFICPBK&limit=mc-loc%3A100600ADFICPBKM&limit=mc-loc%3A100700ADFICPBKSF&limit=mc-loc%3A100800ADFICPBKW&limit=mc-loc%3A320440ADLPAD&limit=mc-loc%3A100850ADFICR&limit=mc-loc%3A100900ADFICSF&limit=mc-loc%3A220400ADVIDVHS&limit=mc-loc%3A101000ADFICW&limit=mc-loc%3A101100KFIC&limit=mc-loc%3A120700KNF&limit=mc-loc%3A101200LPFICCF&limit=mc-loc%3A101300LPFIC&limit=mc-loc%3A140800JUVFICLP&limit=mc-loc%3A101400LPFICM&limit=mc-loc%3A121000LPNF&sort_by=acqdate_dsc&limit=">Historical</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=Horror+fiction&op=and&idx=ti&op=and&idx=nb&do=Search&limit=mc-ccode%3AAB&limit=mc-ccode%3AAUD&limit=mc-loc%3A260100ADAUDCAS&limit=mc-loc%3A260200ADAUDCD&limit=mc-loc%3A260250ADAUDMP3&limit=mc-loc%3A260300ADAUDPL&limit=mc-loc%3A100100ADFICCF&limit=mc-loc%3A100200ADFIC&limit=mc-loc%3A100250ADFICGN&limit=mc-loc%3A100300ADFICHF&limit=mc-loc%3A100450ADFICHOL&limit=mc-loc%3A260350ADAUDMCAS&limit=mc-loc%3A100400ADFICM&limit=mc-loc%3A100500ADFICPBK&limit=mc-loc%3A100600ADFICPBKM&limit=mc-loc%3A100700ADFICPBKSF&limit=mc-loc%3A100800ADFICPBKW&limit=mc-loc%3A320440ADLPAD&limit=mc-loc%3A100850ADFICR&limit=mc-loc%3A100900ADFICSF&limit=mc-loc%3A220400ADVIDVHS&limit=mc-loc%3A101000ADFICW&limit=mc-loc%3A101100KFIC&limit=mc-loc%3A120700KNF&limit=mc-loc%3A101200LPFICCF&limit=mc-loc%3A101300LPFIC&limit=mc-loc%3A140800JUVFICLP&limit=mc-loc%3A101400LPFICM&limit=mc-loc%3A121000LPNF&sort_by=acqdate_dsc&limit=">Horror</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=Christian+fiction&op=and&idx=ti&op=and&idx=nb&do=Search&limit=mc-ccode%3AAB&limit=mc-ccode%3AAUD&limit=mc-loc%3A260100ADAUDCAS&limit=mc-loc%3A260200ADAUDCD&limit=mc-loc%3A260250ADAUDMP3&limit=mc-loc%3A260300ADAUDPL&limit=mc-loc%3A100100ADFICCF&limit=mc-loc%3A100200ADFIC&limit=mc-loc%3A100250ADFICGN&limit=mc-loc%3A100300ADFICHF&limit=mc-loc%3A100450ADFICHOL&limit=mc-loc%3A260350ADAUDMCAS&limit=mc-loc%3A100400ADFICM&limit=mc-loc%3A100500ADFICPBK&limit=mc-loc%3A100600ADFICPBKM&limit=mc-loc%3A100700ADFICPBKSF&limit=mc-loc%3A100800ADFICPBKW&limit=mc-loc%3A320440ADLPAD&limit=mc-loc%3A100850ADFICR&limit=mc-loc%3A100900ADFICSF&limit=mc-loc%3A220400ADVIDVHS&limit=mc-loc%3A101000ADFICW&limit=mc-loc%3A101100KFIC&limit=mc-loc%3A120700KNF&limit=mc-loc%3A101200LPFICCF&limit=mc-loc%3A101300LPFIC&limit=mc-loc%3A140800JUVFICLP&limit=mc-loc%3A101400LPFICM&limit=mc-loc%3A121000LPNF&sort_by=acqdate_dsc&limit=">Inspirational</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=Mystery+fiction&op=and&idx=ti&op=and&idx=nb&do=Search&limit=mc-ccode%3AAB&limit=mc-ccode%3AAUD&limit=mc-loc%3A260100ADAUDCAS&limit=mc-loc%3A260200ADAUDCD&limit=mc-loc%3A260250ADAUDMP3&limit=mc-loc%3A260300ADAUDPL&limit=mc-loc%3A100100ADFICCF&limit=mc-loc%3A100200ADFIC&limit=mc-loc%3A100250ADFICGN&limit=mc-loc%3A100300ADFICHF&limit=mc-loc%3A100450ADFICHOL&limit=mc-loc%3A260350ADAUDMCAS&limit=mc-loc%3A100400ADFICM&limit=mc-loc%3A100500ADFICPBK&limit=mc-loc%3A100600ADFICPBKM&limit=mc-loc%3A100700ADFICPBKSF&limit=mc-loc%3A100800ADFICPBKW&limit=mc-loc%3A320440ADLPAD&limit=mc-loc%3A100850ADFICR&limit=mc-loc%3A100900ADFICSF&limit=mc-loc%3A220400ADVIDVHS&limit=mc-loc%3A101000ADFICW&limit=mc-loc%3A101100KFIC&limit=mc-loc%3A120700KNF&limit=mc-loc%3A101200LPFICCF&limit=mc-loc%3A101300LPFIC&limit=mc-loc%3A140800JUVFICLP&limit=mc-loc%3A101400LPFICM&limit=mc-loc%3A121000LPNF&sort_by=acqdate_dsc&limit=">Mystery</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=Paranormal+fiction&op=and&idx=ti&op=and&idx=nb&do=Search&limit=mc-ccode%3AAB&limit=mc-ccode%3AAUD&limit=mc-loc%3A260100ADAUDCAS&limit=mc-loc%3A260200ADAUDCD&limit=mc-loc%3A260250ADAUDMP3&limit=mc-loc%3A260300ADAUDPL&limit=mc-loc%3A100100ADFICCF&limit=mc-loc%3A100200ADFIC&limit=mc-loc%3A100250ADFICGN&limit=mc-loc%3A100300ADFICHF&limit=mc-loc%3A100450ADFICHOL&limit=mc-loc%3A260350ADAUDMCAS&limit=mc-loc%3A100400ADFICM&limit=mc-loc%3A100500ADFICPBK&limit=mc-loc%3A100600ADFICPBKM&limit=mc-loc%3A100700ADFICPBKSF&limit=mc-loc%3A100800ADFICPBKW&limit=mc-loc%3A320440ADLPAD&limit=mc-loc%3A100850ADFICR&limit=mc-loc%3A100900ADFICSF&limit=mc-loc%3A220400ADVIDVHS&limit=mc-loc%3A101000ADFICW&limit=mc-loc%3A101100KFIC&limit=mc-loc%3A120700KNF&limit=mc-loc%3A101200LPFICCF&limit=mc-loc%3A101300LPFIC&limit=mc-loc%3A140800JUVFICLP&limit=mc-loc%3A101400LPFICM&limit=mc-loc%3A121000LPNF&sort_by=acqdate_dsc&limit=">Paranormal</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=Romance+fiction&op=and&idx=ti&op=and&idx=nb&do=Search&limit=mc-ccode%3AAB&limit=mc-ccode%3AAUD&limit=mc-loc%3A260100ADAUDCAS&limit=mc-loc%3A260200ADAUDCD&limit=mc-loc%3A260250ADAUDMP3&limit=mc-loc%3A260300ADAUDPL&limit=mc-loc%3A100100ADFICCF&limit=mc-loc%3A100200ADFIC&limit=mc-loc%3A100250ADFICGN&limit=mc-loc%3A100300ADFICHF&limit=mc-loc%3A100450ADFICHOL&limit=mc-loc%3A260350ADAUDMCAS&limit=mc-loc%3A100400ADFICM&limit=mc-loc%3A100500ADFICPBK&limit=mc-loc%3A100600ADFICPBKM&limit=mc-loc%3A100700ADFICPBKSF&limit=mc-loc%3A100800ADFICPBKW&limit=mc-loc%3A320440ADLPAD&limit=mc-loc%3A100850ADFICR&limit=mc-loc%3A100900ADFICSF&limit=mc-loc%3A220400ADVIDVHS&limit=mc-loc%3A101000ADFICW&limit=mc-loc%3A101100KFIC&limit=mc-loc%3A120700KNF&limit=mc-loc%3A101200LPFICCF&limit=mc-loc%3A101300LPFIC&limit=mc-loc%3A140800JUVFICLP&limit=mc-loc%3A101400LPFICM&limit=mc-loc%3A121000LPNF&sort_by=acqdate_dsc&limit=">Romance</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=Science+fiction&op=and&idx=ti&op=and&idx=nb&do=Search&limit=mc-ccode%3AAB&limit=mc-ccode%3AAUD&limit=mc-loc%3A260100ADAUDCAS&limit=mc-loc%3A260200ADAUDCD&limit=mc-loc%3A260250ADAUDMP3&limit=mc-loc%3A260300ADAUDPL&limit=mc-loc%3A100100ADFICCF&limit=mc-loc%3A100200ADFIC&limit=mc-loc%3A100250ADFICGN&limit=mc-loc%3A100300ADFICHF&limit=mc-loc%3A100450ADFICHOL&limit=mc-loc%3A260350ADAUDMCAS&limit=mc-loc%3A100400ADFICM&limit=mc-loc%3A100500ADFICPBK&limit=mc-loc%3A100600ADFICPBKM&limit=mc-loc%3A100700ADFICPBKSF&limit=mc-loc%3A100800ADFICPBKW&limit=mc-loc%3A320440ADLPAD&limit=mc-loc%3A100850ADFICR&limit=mc-loc%3A100900ADFICSF&limit=mc-loc%3A220400ADVIDVHS&limit=mc-loc%3A101000ADFICW&limit=mc-loc%3A101100KFIC&limit=mc-loc%3A120700KNF&limit=mc-loc%3A101200LPFICCF&limit=mc-loc%3A101300LPFIC&limit=mc-loc%3A140800JUVFICLP&limit=mc-loc%3A101400LPFICM&limit=mc-loc%3A121000LPNF&sort_by=acqdate_dsc&limit=">Science Fiction</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=suspense&op=and&idx=ti&op=and&idx=nb&do=Search&limit=mc-ccode%3AAB&limit=mc-ccode%3AAUD&limit=mc-loc%3A260100ADAUDCAS&limit=mc-loc%3A260200ADAUDCD&limit=mc-loc%3A260250ADAUDMP3&limit=mc-loc%3A260300ADAUDPL&limit=mc-loc%3A100100ADFICCF&limit=mc-loc%3A100200ADFIC&limit=mc-loc%3A100250ADFICGN&limit=mc-loc%3A100300ADFICHF&limit=mc-loc%3A100450ADFICHOL&limit=mc-loc%3A260350ADAUDMCAS&limit=mc-loc%3A100400ADFICM&limit=mc-loc%3A100500ADFICPBK&limit=mc-loc%3A100600ADFICPBKM&limit=mc-loc%3A100700ADFICPBKSF&limit=mc-loc%3A100800ADFICPBKW&limit=mc-loc%3A320440ADLPAD&limit=mc-loc%3A100850ADFICR&limit=mc-loc%3A100900ADFICSF&limit=mc-loc%3A220400ADVIDVHS&limit=mc-loc%3A101000ADFICW&limit=mc-loc%3A101100KFIC&limit=mc-loc%3A120700KNF&limit=mc-loc%3A101200LPFICCF&limit=mc-loc%3A101300LPFIC&limit=mc-loc%3A140800JUVFICLP&limit=mc-loc%3A101400LPFICM&limit=mc-loc%3A121000LPNF&sort_by=acqdate_dsc&limit=">Suspense</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=Western+fiction&op=and&idx=ti&op=and&idx=nb&do=Search&limit=mc-ccode%3AAB&limit=mc-ccode%3AAUD&limit=mc-loc%3A260100ADAUDCAS&limit=mc-loc%3A260200ADAUDCD&limit=mc-loc%3A260250ADAUDMP3&limit=mc-loc%3A260300ADAUDPL&limit=mc-loc%3A100100ADFICCF&limit=mc-loc%3A100200ADFIC&limit=mc-loc%3A100250ADFICGN&limit=mc-loc%3A100300ADFICHF&limit=mc-loc%3A100450ADFICHOL&limit=mc-loc%3A260350ADAUDMCAS&limit=mc-loc%3A100400ADFICM&limit=mc-loc%3A100500ADFICPBK&limit=mc-loc%3A100600ADFICPBKM&limit=mc-loc%3A100700ADFICPBKSF&limit=mc-loc%3A100800ADFICPBKW&limit=mc-loc%3A320440ADLPAD&limit=mc-loc%3A100850ADFICR&limit=mc-loc%3A100900ADFICSF&limit=mc-loc%3A220400ADVIDVHS&limit=mc-loc%3A101000ADFICW&limit=mc-loc%3A101100KFIC&limit=mc-loc%3A120700KNF&limit=mc-loc%3A101200LPFICCF&limit=mc-loc%3A101300LPFIC&limit=mc-loc%3A140800JUVFICLP&limit=mc-loc%3A101400LPFICM&limit=mc-loc%3A121000LPNF&sort_by=acqdate_dsc&limit=">Western</a></li>
                </ul>
              </div>
              <div class="browse-column">
                <h3>Nonfiction</h3>
                <ul>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=Biography&op=and&idx=ti&op=and&idx=nb&do=Search&limit=mc-ccode%3AAB&limit=mc-ccode%3AAUD&limit=mc-loc%3A260100ADAUDCAS&limit=mc-loc%3A260200ADAUDCD&limit=mc-loc%3A260250ADAUDMP3&limit=mc-loc%3A260300ADAUDPL&limit=mc-loc%3A120100ADNFB&limit=mc-loc%3A100100ADFICCF&limit=mc-loc%3A120200ADNF&limit=mc-loc%3A100700ADFICPBKSF&limit=mc-loc%3A120700KNF&limit=mc-loc%3A121000LPNF&limit=mc-loc%3A121200ADNFQ&sort_by=acqdate_dsc&limit=">Biography</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=Business&op=and&idx=ti&op=and&idx=nb&limit=mc-ccode%3AAB&limit=mc-ccode%3AAUD&limit=mc-loc%3A260100ADAUDCAS&limit=mc-loc%3A260200ADAUDCD&limit=mc-loc%3A260250ADAUDMP3&limit=mc-loc%3A260300ADAUDPL&limit=mc-loc%3A120100ADNFB&limit=mc-loc%3A100100ADFICCF&limit=mc-loc%3A120200ADNF&limit=mc-loc%3A100700ADFICPBKSF&limit=mc-loc%3A120700KNF&limit=mc-loc%3A121000LPNF&limit=mc-loc%3A121200ADNFQ&sort_by=acqdate_dsc">Business</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=Cooking&op=and&idx=ti&op=and&idx=nb&do=Search&limit=mc-ccode%3AAB&limit=mc-ccode%3AAUD&limit=mc-loc%3A260100ADAUDCAS&limit=mc-loc%3A260200ADAUDCD&limit=mc-loc%3A260250ADAUDMP3&limit=mc-loc%3A260300ADAUDPL&limit=mc-loc%3A120100ADNFB&limit=mc-loc%3A100100ADFICCF&limit=mc-loc%3A120200ADNF&limit=mc-loc%3A100700ADFICPBKSF&limit=mc-loc%3A120700KNF&limit=mc-loc%3A121000LPNF&limit=mc-loc%3A121200ADNFQ&sort_by=acqdate_dsc">Cooking</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=Crafts&op=or&idx=su%2Cwrdl&q=Hobbies&op=or&idx=su%2Cwrdl&do=Search&limit=mc-ccode%3AAB&limit=mc-ccode%3AAUD&limit=mc-loc%3A260100ADAUDCAS&limit=mc-loc%3A260200ADAUDCD&limit=mc-loc%3A260250ADAUDMP3&limit=mc-loc%3A260300ADAUDPL&limit=mc-loc%3A120100ADNFB&limit=mc-loc%3A100100ADFICCF&limit=mc-loc%3A120200ADNF&limit=mc-loc%3A100700ADFICPBKSF&limit=mc-loc%3A120700KNF&limit=mc-loc%3A121000LPNF&limit=mc-loc%3A121200ADNFQ&sort_by=acqdate_dsc">Crafts & Hobbies</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=callnum&q=616.&op=and&idx=ti&op=and&idx=nb&do=Search&limit=mc-ccode%3AAB&limit=mc-ccode%3AAUD&limit=mc-loc%3A260100ADAUDCAS&limit=mc-loc%3A260200ADAUDCD&limit=mc-loc%3A260250ADAUDMP3&limit=mc-loc%3A260300ADAUDPL&limit=mc-loc%3A120100ADNFB&limit=mc-loc%3A100100ADFICCF&limit=mc-loc%3A120200ADNF&limit=mc-loc%3A100700ADFICPBKSF&limit=mc-loc%3A120700KNF&limit=mc-loc%3A121000LPNF&limit=mc-loc%3A121200ADNFQ&sort_by=acqdate_dsc">Health & Wellness</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=history&op=and&idx=callnum&q=9*&op=not&idx=callnum&q=0*&op=not&idx=callnum&q=1*&op=not&idx=callnum&q=2*&op=not&idx=callnum&q=3*&op=not&idx=callnum&q=4*&op=not&idx=callnum&q=5*&op=not&idx=callnum&q=6*&op=not&idx=callnum&q=7*&op=not&idx=callnum&q=8*&op=not&idx=callnum&q=920.&do=Search&limit=mc-ccode%3AAB&limit=mc-loc%3A120200ADNF&limit=mc-loc%3A121000LPNF&sort_by=acqdate_dsc&limit=">History</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=callnum&q=500.&op=or&idx=callnum&q=510.&op=or&idx=callnum&q=5*&op=not&idx=callnum&q=0*&op=not&idx=callnum&q=1*&op=not&idx=callnum&q=2*&op=not&idx=callnum&q=3*&op=not&idx=callnum&q=4*&op=not&idx=callnum&q=6*&op=not&idx=callnum&q=7*&op=not&idx=callnum&q=8*&op=not&idx=callnum&q=9*&op=and&idx=kw&do=Search&limit=mc-ccode%3AAB&limit=mc-loc%3A120200ADNF&limit=mc-loc%3A121000LPNF&sort_by=acqdate_dsc&limit=">Math & Science</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=religion&op=and&idx=callnum&q=2*&op=and&idx=kw&do=Search&limit=mc-ccode%3AAB&limit=mc-loc%3A120200ADNF&limit=mc-loc%3A121000LPNF&sort_by=acqdate_dsc">Religion</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=callnum&q=796.&op=and&idx=su%2Cwrdl&q=sports&op=or&idx=su%2Cwrdl&q=Professional+sports&op=or&idx=su%2Cwrdl&q=baseball&op=or&idx=su%2Cwrdl&q=football&op=or&idx=su%2Cwrdl&q=soccer&op=or&idx=su%2Cwrdl&q=tennis&op=or&idx=su%2Cwrdl&q=hockey&op=or&idx=su%2Cwrdl&q=basketball&op=or&idx=su%2Cwrdl&q=racing&op=or&idx=su%2Cwrdl&q=wrestling&do=Search&limit=mc-ccode%3AAB&limit=mc-loc%3A120200ADNF&limit=mc-loc%3A121000LPNF&sort_by=acqdate_dsc">Sports</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=callnum&q=917.&op=and&idx=su%2Cwrdl&q=travel&limit=mc-ccode%3AAB&limit=mc-loc%3A120200ADNF&limit=mc-loc%3A121000LPNF&sort_by=acqdate_dsc">Travel</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=callnum&q=364.15&op=and&idx=callnum&do=Search&limit=mc-ccode%3AAB&limit=mc-loc%3A120200ADNF&limit=mc-loc%3A120400ADNFTC&limit=mc-loc%3A121000LPNF&sort_by=acqdate_dsc">True Crime</a></li>
                </ul>
              </div>
              <div class="browse-column">
                <ul>
                  <li class="browse-la-widget">
    <div class="libraryaware_widget_dc5322d12f5d4494b52fb19da7e1f1c0"></div>
                  </li>
                </ul>
              </div>
            </div>
          </li>
          <li>
            <a href="#">Movies & TV</a>
            <div class="dd-pullright">
              <div class="browse-column">
                <h3>New Arrivals</h3>
                <ul>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=films&op=and&idx=ti&op=and&idx=nb&do=Search&limit=mc-ccode%3ADVD&limit-yr=2017-&sort_by=acqdate_dsc">DVDs</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=films&op=and&idx=ti&op=and&idx=nb&do=Search&limit=mc-ccode%3ABLU&limit-yr=2017-&sort_by=acqdate_dsc">Blu-rays</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=television&op=and&idx=ti&op=and&idx=nb&do=Search&limit=mc-ccode%3ABLU&limit=mc-ccode%3ADVD&limit-yr=2017-&sort_by=acqdate_dsc">TV Series</a></li>
                </ul>
    <h3>Television</h3>
                <ul>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cphr&q=Action+and+adventure+television+programs&op=or&idx=su%2Cphr&do=Search&limit=mc-ccode%3ABLU&limit=mc-ccode%3ADVD&limit=mc-loc%3A220100ADVIDBLU&limit=mc-loc%3A220200ADVIDDVD&sort_by=acqdate_dsc">Action & Adventure</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cphr&q=Television+comedies&op=or&idx=su%2Cphr&do=Search&limit=mc-ccode%3ABLU&limit=mc-ccode%3ADVD&limit=mc-loc%3A220100ADVIDBLU&limit=mc-loc%3A220200ADVIDDVD&sort_by=acqdate_dsc">Comedies</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cphr&q=Television+crime+shows&op=or&idx=su%2Cphr&do=Search&limit=mc-ccode%3ABLU&limit=mc-ccode%3ADVD&limit=mc-loc%3A220100ADVIDBLU&limit=mc-loc%3A220200ADVIDDVD&sort_by=acqdate_dsc">Crime</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cphr&q=Documentary+television+programs&op=or&idx=su%2Cphr&do=Search&limit=mc-ccode%3ABLU&limit=mc-ccode%3ADVD&limit=mc-loc%3A220100ADVIDBLU&limit=mc-loc%3A220200ADVIDDVD&sort_by=acqdate_dsc">Documentaries</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cphr&q=Horror+television+programs&op=or&idx=su%2Cphr&do=Search&limit=mc-ccode%3ABLU&limit=mc-ccode%3ADVD&limit=mc-loc%3A220100ADVIDBLU&limit=mc-loc%3A220200ADVIDDVD&sort_by=acqdate_dsc">Horror</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cphr&q=Reality+television+programs&op=or&idx=su%2Cphr&do=Search&limit=mc-ccode%3ABLU&limit=mc-ccode%3ADVD&limit=mc-loc%3A220100ADVIDBLU&limit=mc-loc%3A220200ADVIDDVD&sort_by=acqdate_dsc">Reality TV</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cphr&q=Science+fiction+television+programs&op=or&idx=su%2Cphr&q=Fantasy+television+programs&do=Search&limit=mc-ccode%3ABLU&limit=mc-ccode%3ADVD&limit=mc-loc%3A220100ADVIDBLU&limit=mc-loc%3A220200ADVIDDVD&sort_by=acqdate_dsc">Sci-Fi & Fantasy</a></li>
                </ul>
              </div>
              <div class="browse-column">
                <h3>Movies</h3>
                <ul>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=Action+and+adventure+films&limit=mc-ccode%3A'BLU'&limit=mc-ccode%3A'DVD'&limit=mc-loc%3A'220100ADVIDBLU'&limit=mc-loc%3A'220200ADVIDDVD'&sort_by=acqdate_dsc">Action & Adventure</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=Animated+films&op=or&idx=su%2Cwrdl&do=Search&limit=mc-ccode%3ABLU&limit=mc-ccode%3ADVD&limit=mc-loc%3A220100ADVIDBLU&limit=mc-loc%3A220200ADVIDDVD&sort_by=acqdate_dsc">Animated</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cphr&q=comedy+films&op=or&idx=su%2Cwrdl&do=Search&limit=mc-ccode%3ABLU&limit=mc-ccode%3ADVD&limit=mc-loc%3A220100ADVIDBLU&limit=mc-loc%3A220200ADVIDDVD&sort_by=acqdate_dsc">Comedies</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cphr&q=documentary+films&op=or&idx=su%2Cwrdl&do=Search&limit=mc-ccode%3ABLU&limit=mc-ccode%3ADVD&limit=mc-loc%3A220100ADVIDBLU&limit=mc-loc%3A220200ADVIDDVD&sort_by=acqdate_dsc">Documentaries</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=drama+film&op=or&idx=su%2Cwrdl&do=Search&limit=mc-ccode%3ABLU&limit=mc-ccode%3ADVD&limit=mc-loc%3A220100ADVIDBLU&limit=mc-loc%3A220200ADVIDDVD&sort_by=acqdate_dsc">Dramas</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cphr&q=horror+films&op=or&idx=su%2Cwrdl&do=Search&limit=mc-ccode%3ABLU&limit=mc-ccode%3ADVD&limit=mc-loc%3A220100ADVIDBLU&limit=mc-loc%3A220200ADVIDDVD&sort_by=acqdate_dsc">Horror</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cphr&q=musical+films&op=or&idx=su%2Cwrdl&do=Search&limit=mc-ccode%3ABLU&limit=mc-ccode%3ADVD&limit=mc-loc%3A220100ADVIDBLU&limit=mc-loc%3A220200ADVIDDVD&sort_by=acqdate_dsc">Musicals</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cphr&q=science+fiction+films&op=or&idx=su%2Cphr&q=fantasy+films&do=Search&limit=mc-ccode%3ABLU&limit=mc-ccode%3ADVD&limit=mc-loc%3A220100ADVIDBLU&limit=mc-loc%3A220200ADVIDDVD&sort_by=acqdate_dsc">Sci-Fi & Fantasy</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cphr&q=Thrillers+(Motion+pictures)&op=or&idx=su%2Cphr&do=Search&limit=mc-ccode%3ABLU&limit=mc-ccode%3ADVD&limit=mc-loc%3A220100ADVIDBLU&limit=mc-loc%3A220200ADVIDDVD&sort_by=acqdate_dsc">Thrillers</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cphr&q=western+films&op=or&idx=su%2Cphr&do=Search&limit=mc-ccode%3ABLU&limit=mc-ccode%3ADVD&limit=mc-loc%3A220100ADVIDBLU&limit=mc-loc%3A220200ADVIDDVD&sort_by=acqdate_dsc">Westerns</a></li>
                </ul>
              </div>
              <div class="browse-column">

              </div>
            </div>
          </li>
          <li>
            <a href="#">Teens</a>
            <div class="dd-pullright">
              <div class="browse-column">
                <h3>New Arrivals</h3>
                <ul>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=kw&op=and&idx=ti&op=and&idx=nb&limit=mc-loc%3A101800YAFIC&limit=mc-loc%3A102000YAFICPBKF&limit=mc-loc%3A102100YAFICSF&limit-yr=2017-&sort_by=acqdate_dsc">Fiction</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=kw&op=and&idx=ti&op=and&idx=nb&limit=mc-loc%3A121600YANFB&limit=mc-loc%3A121700YANF&limit-yr=2017-&sort_by=acqdate_dsc">Nonfiction</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=kw&op=and&idx=ti&op=and&idx=nb&limit=mc-loc%3A101900YAFICGN&limit-yr=2017-&sort_by=acqdate_dsc">Graphic Novels</a></li>
                </ul>
                <h3>Graphic novels</h3>
                <ul>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=adventure&op=or&idx=su%2Cwrdl&q=adventurers&op=or&idx=su%2Cwrdl&q=adventures&limit=mc-loc%3A'100250ADFICGN'&limit=mc-loc%3A'101900YAFICGN'&offset=0&sort_by=acqdate_dsc">Adventure</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=magic&op=+or+&idx=su%2Cwrdl&q=fantasy&op=+or+&idx=nb&q=hero&limit=mc-loc%3A'100250ADFICGN'&limit=mc-loc%3A'101900YAFICGN'&sort_by=acqdate_dsc">Fantasy</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=horror&op=and&idx=ti&op=and&idx=nb&do=Search&limit=mc-loc%3A101900YAFICGN&sort_by=acqdate_dsc">Horror</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=kw&q=manga&op=and&idx=ti&op=and&idx=nb&do=Search&limit=mc-loc%3A101900YAFICGN&sort_by=acqdate_dsc">Manga</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=science+fiction&op=and&idx=ti&op=and&idx=nb&do=Search&limit=mc-loc%3A101900YAFICGN&sort_by=acqdate_dsc">Science Fiction</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=heroes&op=or&idx=su%2Cwrdl&q=superheroes&op=or&idx=su%2Cwrdl&q=hero&op=or&idx=su%2Cwrdl&q=superhero&limit=mc-loc%3A'100250ADFICGN'&limit=mc-loc%3A'101900YAFICGN'&offset=0&sort_by=acqdate_dsc">Heroes & Superheroes</a></li>
                </ul>
              </div>
              <div class="browse-column">
                <h3>Browse</h3>
                <ul>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=Adventure&op=+or+&idx=su%2Cwrdl&q=Adventurers&op=+or+&idx=su%2Cwrdl&q=Survival&limit=mc-loc%3A'260500YAAUDCAS'&limit=mc-loc%3A'260600YAAUDCD'&limit=mc-loc%3A'121600YANFB'&limit=mc-loc%3A'101800YAFIC'&limit=mc-loc%3A'121700YANF'&limit=mc-loc%3A'102000YAFICPBKF'&limit=mc-loc%3A'102100YAFICSF'&sort_by=acqdate_dsc">Adventure & Survival</a></li>
                  <li><a href="/cgi-bin/koha/opac-shelves.pl?op=view&shelfnumber=2963&sortfield=title">Books to Movies</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=Fantasy&op=+or+&idx=su%2Cwrdl&q=Magic&op=+or+&idx=su%2Cwrdl&q=Wizards&limit=mc-loc%3A'260500YAAUDCAS'&limit=mc-loc%3A'260600YAAUDCD'&limit=mc-loc%3A'121600YANFB'&limit=mc-loc%3A'101800YAFIC'&limit=mc-loc%3A'121700YANF'&limit=mc-loc%3A'102000YAFICPBKF'&limit=mc-loc%3A'102100YAFICSF'&sort_by=acqdate_dsc">Fantasy</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=Horror&limit=mc-loc%3A'260500YAAUDCAS'&limit=mc-loc%3A'260600YAAUDCD'&limit=mc-loc%3A'121600YANFB'&limit=mc-loc%3A'101800YAFIC'&limit=mc-loc%3A'121700YANF'&limit=mc-loc%3A'102000YAFICPBKF'&limit=mc-loc%3A'102100YAFICSF'&sort_by=acqdate_dsc">Horror</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=Mystery&op=+or+&idx=su%2Cwrdl&q=Crime&op=+or+&idx=su%2Cwrdl&q=Criminal&op=+or+&idx=su%2Cwrdl&q=Detective&op=+or+&idx=su%2Cwrdl&q=Murder&limit=mc-loc%3A'260500YAAUDCAS'&limit=mc-loc%3A'260600YAAUDCD'&limit=mc-loc%3A'121600YANFB'&limit=mc-loc%3A'101800YAFIC'&limit=mc-loc%3A'121700YANF'&limit=mc-loc%3A'102000YAFICPBKF'&limit=mc-loc%3A'102100YAFICSF'&sort_by=acqdate_dsc">Murder & Mystery</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=Romance&op=or&idx=su%2Cwrdl&q=Love&op=or&idx=su%2Cwrdl&q=Man-woman+relationships&op=or&idx=su%2Cwrdl&q=Dating&do=Search&limit=mc-loc%3A260500YAAUDCAS&limit=mc-loc%3A260600YAAUDCD&limit=mc-loc%3A121600YANFB&limit=mc-loc%3A101800YAFIC&limit=mc-loc%3A121700YANF&limit=mc-loc%3A102000YAFICPBKF&limit=mc-loc%3A102100YAFICSF&sort_by=acqdate_dsc">Romance</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=science+fiction&op=or&idx=su%2Cwrdl&q=time+travel&do=Search&limit=mc-loc%3A260500YAAUDCAS&limit=mc-loc%3A260600YAAUDCD&limit=mc-loc%3A121600YANFB&limit=mc-loc%3A101800YAFIC&limit=mc-loc%3A121700YANF&limit=mc-loc%3A102000YAFICPBKF&limit=mc-loc%3A102100YAFICSF&sort_by=acqdate_dsc">Sci-Fi</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=sports&op=or&idx=su%2Cwrdl&q=baseball&op=or&idx=su%2Cwrdl&q=basketball&op=or&idx=su%2Cwrdl&q=boxing&op=or&idx=su%2Cwrdl&q=football&op=or&idx=su%2Cwrdl&q=soccer&do=Search&limit=mc-loc%3A260500YAAUDCAS&limit=mc-loc%3A260600YAAUDCD&limit=mc-loc%3A121600YANFB&limit=mc-loc%3A101800YAFIC&limit=mc-loc%3A121700YANF&limit=mc-loc%3A102000YAFICPBKF&limit=mc-loc%3A102100YAFICSF&sort_by=acqdate_dsc">Sports</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=supernatural&op=or&idx=su%2Cwrdl&q=ghosts&op=or&idx=su%2Cwrdl&q=haunted&op=or&idx=su%2Cwrdl&q=monsters&op=or&idx=su%2Cwrdl&q=paranormal&op=or&idx=su%2Cwrdl&q=vampires&op=or&idx=su%2Cwrdl&q=werewolves&op=or&idx=su%2Cwrdl&q=zombies&do=Search&limit=mc-loc%3A260500YAAUDCAS&limit=mc-loc%3A260600YAAUDCD&limit=mc-loc%3A121600YANFB&limit=mc-loc%3A101800YAFIC&limit=mc-loc%3A121700YANF&limit=mc-loc%3A102000YAFICPBKF&limit=mc-loc%3A102100YAFICSF&sort_by=acqdate_dsc">Supernatural</a></li>
                </ul>
              </div>
              <div class="browse-column">
                <ul>
                  <li class="browse-la-widget">
    <div class="libraryaware_widget_408cccb202ea4819a44481fc0b117649"></div>

                  </li>
                </ul>
              </div>
            </div>
          </li>    
          <li>
            <a href="#">Kids</a>
            <div class="dd-pullright">
              <div class="browse-column">
                <h3>New Arrivals</h3>
                <ul>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=kw&op=and&idx=ti&op=and&idx=nb&limit=mc-ccode%3AJB&limit=mc-loc%3A140100JUVFICBR&limit=mc-loc%3A140200JUVFICBB&limit=mc-loc%3A140350JUVFICCHI&limit=mc-loc%3A140450JUVFICP&limit-yr=2017-&sort_by=acqdate_dsc">Picture Books & Early Readers</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=kw&op=and&idx=ti&op=and&idx=nb&limit=mc-ccode%3AJB&limit=mc-loc%3A140325JUVFICBC&limit=mc-loc%3A140500JUVFIC&limit-yr=2017-&sort_by=acqdate_dsc">Chapter Books</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=kw&op=and&idx=ti&op=and&idx=nb&limit=mc-ccode%3AJB&limit=mc-loc%3A140600JUVFICGN&limit-yr=2017-&sort_by=acqdate_dsc">Graphic Novels</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=kw&op=and&idx=ti&op=and&idx=nb&limit=mc-ccode%3AJB&limit=mc-loc%3A160200JUVNF&limit=mc-loc%3A160300JUVNFREF&limit-yr=2017-&sort_by=acqdate_dsc">Non-Fiction</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=kw&op=and&idx=ti&op=and&idx=nb&limit=mc-loc%3A280100JUVAUDBAC&limit=mc-loc%3A280200JUVAUDCAS&limit=mc-loc%3A280300JUVAUDCD&limit=mc-loc%3A280400JUVAUDPL&limit-yr=2017-&sort_by=acqdate_dsc">Audiobooks</a></li>
                </ul>
                <h3>Popular Series</h3>
                <ul>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=ti&q=bad+kitty&op=and&idx=au%2Cwrdl&q=bruel&op=and&idx=nb&do=Search&sort_by=pubdate_dsc">Bad Kitty</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=ti&q=big+nate&op=and&idx=au%2Cwrdl&q=peirce&op=and&idx=nb&do=Search&sort_by=pubdate_dsc">Big Nate</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=ti%2Cphr&q=Diary+of+a+wimpy+kid&op=and&idx=ti&op=and&idx=nb&sort_by=pubdate_dsc">Diary of a Wimpy Kid</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=ti&q=dog+man&op=and&idx=au%2Cwrdl&q=pilkey&op=and&idx=nb&do=Search&sort_by=pubdate_dsc">Dog Man</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=ti&q=dork+diaries&op=and&idx=au%2Cwrdl&q=russell&op=and&idx=nb&do=Search&sort_by=pubdate_dsc">Dork Diaries</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=ti&q=Harry+Potter&op=and&idx=au%2Cwrdl&q=rowling&op=and&idx=nb&do=Search&sort_by=pubdate_dsc">Harry Potter</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=ti&q=i+survived&op=and&idx=au%2Cwrdl&q=tarshis&op=and&idx=nb&do=Search&sort_by=pubdate_dsc">I Survived...</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=ti&q=Magic+Tree+House&op=and&idx=au%2Cwrdl&q=osborne&op=and&idx=nb&do=Search&sort_by=pubdate_dsc">Magic Tree House</a></li>
                </ul>
              </div>
              <div class="browse-column">
                <h3>Nonfiction</h3>
                <ul>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=animals&op=or&idx=su%2Cwrdl&q=wildlife&op=or&idx=su%2Cwrdl&q=pets&do=Search&limit=mc-loc%3A160200JUVNF&sort_by=acqdate_dsc">Animals</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=handicraft&op=or&idx=su%2Cwrdl&q=crafts&op=or&idx=su%2Cwrdl&q=drawing&op=or&idx=su%2Cwrdl&do=Search&limit=mc-loc%3A160100JUVNFB&limit=mc-loc%3A160200JUVNF&sort_by=acqdate_dsc">Arts & Crafts</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=Biography&op=and&idx=ti&do=Search&limit=mc-loc%3A160100JUVNFB&limit=mc-loc%3A160200JUVNF&sort_by=acqdate_dsc">Biographies</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=automobiles&op=or&idx=su%2Cwrdl&q=trains&op=or&idx=su%2Cwrdl&q=transportation&op=or&idx=su%2Cwrdl&q=construction+equipment&op=or&idx=su%2Cwrdl&q=vehicles&do=Search&limit=mc-loc%3A160200JUVNF&sort_by=acqdate_dsc">Cars, Trains & More</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=cooking&op=and&idx=kw&do=Search&limit=mc-loc%3A160200JUVNF&sort_by=acqdate_dsc">Cooking</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=fairy+tales&op=and&idx=kw&do=Search&limit=mc-loc%3A160200JUVNF&sort_by=acqdate_dsc">Fairy Tales</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=geography&op=and&idx=kw&do=Search&limit=mc-loc%3A160200JUVNF&sort_by=acqdate_dsc">Geography</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=history&op=and&idx=callnum&q=900&do=Search&limit=mc-loc%3A160200JUVNF&sort_by=acqdate_dsc">History</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=science&op=and&idx=callnum&q=500&do=Search&limit=mc-loc%3A160200JUVNF&sort_by=acqdate_dsc">Science</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?idx=su%2Cwrdl&q=sports&op=and&idx=ti&op=and&idx=nb&limit=mc-loc%3A160100JUVNFB&limit=mc-loc%3A160200JUVNF&sort_by=acqdate_dsc">Sports</a></li>
                </ul>
                <h3>Movies & TV</h3>
                <ul>
                  <li><a href="/cgi-bin/koha/opac-search.pl?&do=Search&limit=mc-loc%3A240200JUVVIDDVD&sort_by=acqdate_dsc">DVDs</a></li>
                  <li><a href="/cgi-bin/koha/opac-search.pl?&do=Search&limit=mc-loc%3A240100JUVVIDBLU&sort_by=acqdate_dsc">Blu-rays</a></li>
                  <li><a href="/cgi-bin/koha/opac-shelves.pl?op=view&shelfnumber=2962&sortfield=title">Books to Movies</a></li>
                </ul>
              </div>
              <div class="browse-column">
                <ul>
                  <li class="browse-la-widget">
    <div class="libraryaware_widget_22f3d77f1859469c916da2fe7f637026"></div>
                  </li>
                </ul>
              </div>
            </div>
          </li>
        </ul>
      </li>
    </ul>
```
## CSS
```css
    /*browse menu*/
    #browse-menu {
       font-family: Roboto, Arial;
    }

    #browse-menu {
        background-color: #fcb03f;
        list-style: outside none none;
        /*margin: 0 0 0 -20px;*/
        padding: 1em;
        text-align: center;
        width: 16em;
    }

    #browse {
        color: white;
    }

    #browse-menu a {
        text-decoration: none;
        color: #d5d5d5;
    }

    #browse-menu a:hover {
        color: #319cce;
    }

    .dd-pullright {
        background-color: #3A3A3A;
        float: left;
        height: 32em;
        left: -999em;
        margin: 0;
        min-width: 50em;
        position: absolute;
        list-style: none;
    }

    #browse-column > ul > li > a {
       color: #d5d5d5;
    }

    #browse-column > ul > li > a:hover {
       color: #319cce;
    }

    .browse-vert-menu li:hover .dd-pullright {
        left: 16em;
        top: 0;
        z-index: 5;
    }

    #browse-menu:hover .browse-vert-menu {
        top: 12.15em; /*This is a static position that needs adjusted*/
        margin-left: -1em;
    }

    .browse-column {
        display: inline;
        float: left;
        margin: 0.5em 1em 2em 2em;
        min-width: 12em;
        position: relative;
    }

    .browse-column > h3 {
        border-bottom: 1px solid;
        color: #d5d5d5;
        margin-bottom: 5px;
    }

    .browse-column > ul {
        margin: 0;
    	padding-left: 0;
    }

    .browse-column > ul > li {
        list-style: outside none none;
    }

    .browse-vert-menu {
        background-color: #3A3A3A;
        border-right: 0.18em solid #676767;
        height: 32em;
        list-style: outside none none;
        padding: 0;
        position: absolute;
        top: -999em;
        width: 16em;
        z-index: 1000;
    }

    .browse-vert-menu > li {
        padding: 0.75em 1.5em;
        text-align: left;
        width: 16em;
    }

    .browse-vert-menu > li:hover {
        background-color: #4A4A4A;
        border-right: 0.25em solid #319cce;
    }

    .browse-la-widget {
        margin-top: 35px;
    }
```