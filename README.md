RichText Annotator Plugin
==================
##RichText Annotator Plugin

richText-annotator.js is a plugin for Annotator to expand the posibilities typing annotations. For this task, the RichText plugin is using the [Tinymce plugin](http://www.tinymce.com/) replaced by plain text field.

The rich media give you the possibility to add pictures, movies, sounds, rich text... in your annotations.The code is written in javascript/jquery, but you can translate to coffee using [js2coffee](http://js2coffee.org/), the language used in Annotator.

This plugin will be used in [Open Video Annotation tool](http://www.openvideoannotation.org/). 
A project supported by [Center for Hellenic Studies](http://chs.harvard.edu/), at [Harvard University](http://www.harvard.edu/) and the [Becas Talentia](http://www.juntadeandalucia.es/economiainnovacionyciencia/talentia/) program from the Junta de Andalucia, Spain.

##Live-Demo

There is a demo of the RichText Annotator plugin in the next webpage:

http://danielcebrian.com/richText-annotation/demo.html

##Installation

To use the tool you need to install the [Annotator plugin](https://github.com/okfn/annotator/) to annotate text and the [Tinymce plugin](http://www.tinymce.com/) for expanding the rich media.

In addition, add richText-annotator.min.js and richText-annotator.min.css CDN distributed file to your head tag, like this:

```html
	<head>
		<!-- Annotator -->
		<script src="http://ajax.googleapis.com/ajax/libs/jquery/1.7/jquery.min.js"></script>
		<script src="http://assets.annotateit.org/annotator/v1.2.7/annotator-full.min.js"></script>
		<link rel="stylesheet" href="http://assets.annotateit.org/annotator/v1.2.7/annotator.min.css">

		<!-- richText Pluging -->
		<script src="lib/tinymce/tinymce.min.js"></script><!--tinymce for richText-->
		<script src="src/richText-annotator.js"></script>
		<link href="src/richText-annotator.css" rel="stylesheet">
	
	</head>
```

Furthermore, you will need to create an instance of Annotator with the plugin, as follow:

```js
	<script>
    	var optionsRichText = {
    		tinymce:{
				selector: "li.annotator-item textarea",
				plugins: "media image insertdatetime link code",
				menubar: false,
				toolbar_items_size: 'small',
				extended_valid_elements : "iframe[src|frameborder|style|scrolling|class|width|height|name|align|id]",
				toolbar: "insertfile undo redo | styleselect | bold italic | alignleft aligncenter alignright alignjustify | bullist numlist outdent indent | link image media rubric | code ",
    		}
		};
    	$('#div_id').annotator().annotator('addPlugin','RichText',optionsRichText);
    </script>
```

Change #div_id for the real id where the Annotator is and "optionsRichText" is the tinymce options.

##Change the buttons in richText plugin

It is easy to change the number of buttons in the richText plugin. You just need to add "optionsRichText" to the init instance of Annotator and select what you want to see. All these options are explained in [Tinymce plugin](http://www.tinymce.com/).

Of course, you could modify this plugin to add your own button like I have created with "rubric" button. This button is for testing the power of this tinymce plugin. [Rubric is a Tool for assessing by competencies](https://gteavirtual.org/rubric/), you can remove this button removing the "rubric" in the init options of tinymce.

