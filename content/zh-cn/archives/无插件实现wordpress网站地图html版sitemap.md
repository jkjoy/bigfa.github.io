---
title: 无插件实现wordpress网站地图html版sitemap
id: 478
date: 2023-10-17 08:43:40
auther: admin
excerpt: 
permalink: /archives/%E6%97%A0%E6%8F%92%E4%BB%B6%E5%AE%9E%E7%8E%B0wordpress%E7%BD%91%E7%AB%99%E5%9C%B0%E5%9B%BEhtml%E7%89%88sitemap
categories:
tags: 
 - wordpress
---



HTML版代码如下，在模板页面新建sitemap.php文件,后台新建页面-模板选择为sitemap，然后固定链接可以设置为sitemap即可  

```php
<?php
/*
 Template Name: Sitemap
*/
?>
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head profile="http://gmpg.org/xfn/11">
<meta http-equiv="Content-Type" content="text/html; charset=<?php bloginfo( 'charset' ); ?>" />
<title>站点地图 - <?php bloginfo('name'); ?></title>
<meta name="keywords" content="站点地图,<?php bloginfo('name'); ?>" />
<meta name="copyright" content="<?php bloginfo('name'); ?>" />
<link rel="canonical" href="<?php echo get_permalink(); ?>" />
<style type="text/css">
    body {font-family: Microsoft Yahei,Verdana;font-size:13px;margin:0 auto;color: #000000;background: #ffffff;width: 990px;margin: 0 auto}
    a:link,a:visited {color:#000;text-decoration:none;}
    a:hover {color:#08d;text-decoration:none;}
    h1,h2,h3,h4,h5,h6 {font-weight:normal;}
    img {border:0;}
    li {margin-top: 8px;}
    .page {padding: 4px; border-top: 1px #EEEEEE solid}
    .author {background-color:#EEEEFF; padding: 6px; border-top: 1px #ddddee solid}
    #nav, #content, #footer {padding: 8px; border: 1px solid #EEEEEE; clear: both; width: 95%; margin: auto; margin-top: 10px;}
</style>
</head>
<body vlink="#333333" link="#333333">
<h2 style="text-align: center; margin-top: 20px"><?php bloginfo('name'); ?>'s SiteMap </h2>
<center></center>
<div id="nav"><a href="<?php bloginfo('url'); ?>/"><strong><?php bloginfo('name'); ?></strong></a> » <a href="<?php echo get_permalink(); ?>">站点地图</a></div>
<div id="content">
<h3>最新文章</h3>
<ul>
<?php
$previous_year = $year = 0;
$previous_month = $month = 0;
$ul_open = false;
$myposts = get_posts('numberposts=-1&orderby=post_date&order=DESC');
foreach($myposts as $post) :
?>
<li><a href="<?php the_permalink(); ?>" title="<?php the_title(); ?>" target="_blank"><?php the_title(); ?></a></li>
<?php endforeach; ?>
</ul>
</div>
<div id="content">
<li class="categories">分类目录<ul>
<?php wp_list_categories('title_li='); ?>
</ul></li>
</div>
<div id="content">
<li class="categories">单页面</li>
<?php wp_page_menu( $args ); ?>
</div>
<div id="footer">查看博客首页: <strong><a href="<?php bloginfo('url'); ?>/"><?php bloginfo('name'); ?></a></strong></div><br />
<center>
<div style="text-algin: center; font-size: 11px"><strong><a href="http://www.asbid.cn/sitemap_baidu.xml" target="_blank">Baidu-SiteMap</a></strong> Latest Update: <?php $last = $wpdb->get_results("SELECT MAX(post_modified) AS MAX_m FROM $wpdb->posts WHERE (post_type = 'post' OR post_type = 'page') AND (post_status = 'publish' OR post_status = 'private')");$last = date('Y-m-d G:i:s', strtotime($last[0]->MAX_m));echo $last; ?><br /><br /></div>
</center>
</body>
</html>
```