---
layout: blog_page
---

<div class="container">

{% for post in site.posts %}

    {% if post.category contains 'blog' %}

    <div class="row">

      <div class="panel panel-default">

        <div class="panel-body">

            <div class="col-md-2">
                {% if post.thumbnail %}
                    <img src="{{ post.thumbnail }}" style="width: 280px"/>
                {% else %}
                    <img src="img/ads_logo.png" style="width: 280px"/>
                {% endif %}
            </div>

            <div class="col-md-2"></div>

            <div class="col-md-8">
                <h2>
                    <a href="{{ site.baseurl }}{{ post.url }}">{{post.title}}</a><br><small>{{ post.date | date_to_string }}</small>
                </h2>

                <p>
                    {{ post.content | strip_html | truncatewords:40 }}
                </p>
            </div>

        </div>

        <div class="panel-footer">

            <span class="label label-success">
                author: {{ post.author }}
            </span>
            &nbsp;
            <span class="label label-primary">
                category: {{ post.label }}
            </span>

        </div>



      </div>
    </div>

    {% endif %}

{% endfor %}

</div>