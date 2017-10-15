Post's thumbnail text displays author's info, instead of post' description:

First:
    <p>{% if post.description %}{{ post.description }}{% else %}
    {{ post.content | strip html | truncatewords: 15 }}{% endif %}</p>
    
And then, of course, you have to provide a desciption in your post's header
