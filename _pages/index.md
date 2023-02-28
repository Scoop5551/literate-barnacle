---
layout: home
permalink: /
---
<section id="categories" class="container">
    <div class="row">
    {% for category in site.categories %}
    <div class="col-md-4">
        <a href="{{ category.url }}" class="category-link">
            <figure class="category-thumb">
                {% assign category_img_src = "assets/images/categories/" | append: category.slug | append: ".jpg" %}
                <img src="{{ site.baseurl }}{{ category_img_src }}" class="w-50" alt="{{ category.title }}">
            </figure>
            <div class="cat-box">
                <h4 class="category-name">{{ category.title }}</h4>
            </div><!--  /.cat-box -->
        </a>
    </div><!--  /.col-md-4 -->
    {% endfor %}
    </div>
</section>

<section id="products">
    <div class="row">
    {% assign homepage_products = site.products | sort: "ds_position_homepage" %}
    {% for product in homepage_products %}
    {% if product.ds_position_homepage %}
    <div class="col">
        <span>{{ product.title }}</span>
    </div>
    {% endif %}
    {% endfor %}
    </div>
</section>