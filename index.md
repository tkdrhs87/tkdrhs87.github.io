---
layout : default
---

<div class="row">
    {% for post in site.posts %}
    <div class="col-sm-4">
        <div class="panel panel-success">
            <div class="panel-heading">
                <h3 class="panel-title">{{post.title}}</h3>
            </div>
            <div class="panel-body" style="text-align:center;">
                <a href="{{post.url}}">내용 보기</a>
            </div>
        </div>
    </div>
    {% endfor %}
</div>