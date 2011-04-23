This is a tiny helper to protect your users from the social world.

To use it, get your html chunk the way you like it from your social network
provider.
Instead of embedding it directly, create a small element in your page and use
the provided javascript function. It will add an onClick handler to your
element and replace the element with your code.
This code is not in production. It is just a proof of concept for a
presentation.
The code needs jquery, but it should be trivial to rewrite it to another
library if you don't use jquery.

Ignoring any best practices here is a small example with the js file embedded:

<html>
  <body>
    <style type="text/css">
    .camisinha {
        border: 1px solid #205C90;
        border-radius: 6px;
        padding: 3px;
        padding-left: 24px;
        background-image: url("thumbsup.png");
        display: inline;
        background-color: #DDD;
        background-repeat: no-repeat;
    }
    </style>
    <div class="camisinha">Tell the world you like it!</div>
    <script type="text/javascript">
      //<![CDATA[
      (function($){
        function camisinha_social(target, embed_html){
          $(target).click(function(){
            $(this).replaceWith(embed_html);
          });
        }
        $(document).ready(function(){
          var facebook = '<iframe src="http://www.facebook.com/plugins/like.php?href&amp;layout=standard&amp;show_faces=true&amp;width=450&amp;action=like&amp;font&amp;colorscheme=light&amp;height=80" scrolling="no" frameborder="0" style="border:none; overflow:hidden; width:450px; height:80px;" allowTransparency="true"><'+'/iframe>';
          camisinha_social(".camisinha", facebook)
        });
      })(jQuery);

//]]>
    </script>
  </body>
