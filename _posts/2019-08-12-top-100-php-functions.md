---
layout: post
title: "最常使用的 PHP 的 100 个语言内置函数"
description: "为公司上市而学习技术."
date: 2019-08-12
tags: [提高姿势水平]
comments: true
share: true
---

> 为公司上市而学习技术.

目录:

* TOC
{:toc}


这两天家里有事儿, 疏于对技术的学习, 惭愧.


## Exakat 安利


本文摘自于 May 31, 2018 发布的 [The 100 PHP functions that you have to know](https://www.exakat.io/top-100-php-functions/). 所有者是 [EXAKAT](https://www.exakat.io), 那他们家的这个东西是干什么用的呢: 

> Exakat is a tool for analyzing, reporting and assessing PHP code source efficiently and systematically. Exakat processes PHP 5.2 to 7.4 code, as well as reporting on security, performance, code quality, migration.
> 
> Exakat reads the code, builds an AST and several dependency graphs, then indexes all of it in a graph database. From there, exakat runs analysis, collecting potential errors and descriptive information about the code. Finally, exakat produces reports, both for humans and machines.

这边儿有个 [Exakat的社区版下载](https://www.exakat.io/download-exakat/), 不过我说实话目前没有做 code review 的打算, 留着以后用吧. 有条件的旁友也可以支持一下他们家的 Exakat Cloud 或是搞个专家咨询服务.


Exakat的文档在这里: [Exakat的文档](https://exakat.readthedocs.io/en/latest/), 也可以下下来什么的.

另外他们的官博也有些不错的实践参考. 可以慢慢翻一下.


## The 100 PHP functions that you have to know



Here is the top 100 PHP functions : it is the list of the most often used PHP native functions.

The functions are named, and ranked from 1 to 100. The other 4500 functions are not ranked now. The frequency column represents how often this function is used across PHP code : the reference corpus is a list of 1900 PHP open source projects. They were audited with Exakat static analysis engine, version 1.2.5. The average is the number of time a function is called within one project. Some function are used in isolation, and others are a staple.

For example, 4 project out of 5 uses the count function, and when used, the function is called around 150 times. It is both a popular and heavily used function.

Click on the link to go to the documentation. Some insight at the bottom of the top 100.



<table>
<tbody>
<tr>
<td><strong>Rank</strong></td>
<td><strong>Function</strong></td>
<td><strong>Frequency</strong></td>
<td><strong>Average</strong></td>
</tr>
<tr>
<td>1</td>
<td><a href="http://php.net/count">count</a></td>
<td>81.41 %</td>
<td>147.67</td>
</tr>
<tr>
<td>2</td>
<td><a href="http://php.net/is_array">is_array</a></td>
<td>77.32 %</td>
<td>117.86</td>
</tr>
<tr>
<td>3</td>
<td><a href="http://php.net/substr">substr</a></td>
<td>74.62 %</td>
<td>142.92</td>
</tr>
<tr>
<td>4</td>
<td><a href="http://php.net/in_array">in_array</a></td>
<td>74.16 %</td>
<td>79.55</td>
</tr>
<tr>
<td>5</td>
<td><a href="http://php.net/explode">explode</a></td>
<td>73.19 %</td>
<td>71.51</td>
</tr>
<tr>
<td>6</td>
<td><a href="http://php.net/str_replace">str_replace</a></td>
<td>72.32 %</td>
<td>101.05</td>
</tr>
<tr>
<td>7</td>
<td><a href="http://php.net/implode">implode</a></td>
<td>72.27 %</td>
<td>66.59</td>
</tr>
<tr>
<td>8</td>
<td><a href="http://php.net/strlen">strlen</a></td>
<td>70.07 %</td>
<td>98.32</td>
</tr>
<tr>
<td>9</td>
<td><a href="http://php.net/array_merge">array_merge</a></td>
<td>69.46 %</td>
<td>64.01</td>
</tr>
<tr>
<td>10</td>
<td><a href="http://php.net/strpos">strpos</a></td>
<td>67.98 %</td>
<td>78.18</td>
</tr>
<tr>
<td>11</td>
<td><a href="http://php.net/preg_match">preg_match</a></td>
<td>67.31 %</td>
<td>76.60</td>
</tr>
<tr>
<td>12</td>
<td><a href="http://php.net/sprintf">sprintf</a></td>
<td>67.16 %</td>
<td>119.46</td>
</tr>
<tr>
<td>13</td>
<td><a href="http://php.net/trim">trim</a></td>
<td>66.75 %</td>
<td>81.28</td>
</tr>
<tr>
<td>14</td>
<td><a href="http://php.net/strtolower">strtolower</a></td>
<td>65.99 %</td>
<td>59.62</td>
</tr>
<tr>
<td>15</td>
<td><a href="http://php.net/file_exists">file_exists</a></td>
<td>65.12 %</td>
<td>45.13</td>
</tr>
<tr>
<td>16</td>
<td><a href="http://php.net/is_string">is_string</a></td>
<td>61.39 %</td>
<td>45.10</td>
</tr>
<tr>
<td>17</td>
<td><a href="http://php.net/preg_replace">preg_replace</a></td>
<td>60.27 %</td>
<td>54.28</td>
</tr>
<tr>
<td>18</td>
<td><a href="http://php.net/file_get_contents">file_get_contents</a></td>
<td>59.96 %</td>
<td>20.71</td>
</tr>
<tr>
<td>19</td>
<td><a href="http://php.net/array_key_exists">array_key_exists</a></td>
<td>59.70 %</td>
<td>57.50</td>
</tr>
<tr>
<td>20</td>
<td><a href="http://php.net/array_keys">array_keys</a></td>
<td>59.35 %</td>
<td>39.59</td>
</tr>
<tr>
<td>21</td>
<td><a href="http://php.net/dirname">dirname</a></td>
<td>56.44 %</td>
<td>54.84</td>
</tr>
<tr>
<td>22</td>
<td><a href="http://php.net/function_exists">function_exists</a></td>
<td>53.58 %</td>
<td>42.62</td>
</tr>
<tr>
<td>23</td>
<td><a href="http://php.net/array_map">array_map</a></td>
<td>53.22 %</td>
<td>19.45</td>
</tr>
<tr>
<td>24</td>
<td><a href="http://php.net/get_class">get_class</a></td>
<td>53.12 %</td>
<td>33.07</td>
</tr>
<tr>
<td>25</td>
<td><a href="http://php.net/class_exists">class_exists</a></td>
<td>52.50 %</td>
<td>23.13</td>
</tr>
<tr>
<td>26</td>
<td><a href="http://php.net/is_object">is_object</a></td>
<td>51.94 %</td>
<td>35.35</td>
</tr>
<tr>
<td>27</td>
<td><a href="http://php.net/time">time</a></td>
<td>51.79 %</td>
<td>41.42</td>
</tr>
<tr>
<td>28</td>
<td><a href="http://php.net/json_encode">json_encode</a></td>
<td>51.48 %</td>
<td>24.81</td>
</tr>
<tr>
<td>29</td>
<td><a href="http://php.net/date">date</a></td>
<td>50.72 %</td>
<td>52.18</td>
</tr>
<tr>
<td>30</td>
<td><a href="http://php.net/is_null">is_null</a></td>
<td>49.69 %</td>
<td>60.52</td>
</tr>
<tr>
<td>31</td>
<td><a href="http://php.net/is_numeric">is_numeric</a></td>
<td>49.49 %</td>
<td>40.69</td>
</tr>
<tr>
<td>32</td>
<td><a href="http://php.net/array_shift">array_shift</a></td>
<td>49.49 %</td>
<td>23.28</td>
</tr>
<tr>
<td>33</td>
<td><a href="http://php.net/defined">defined</a></td>
<td>48.72 %</td>
<td>86.82</td>
</tr>
<tr>
<td>34</td>
<td><a href="http://php.net/is_dir">is_dir</a></td>
<td>48.57 %</td>
<td>22.86</td>
</tr>
<tr>
<td>35</td>
<td><a href="http://php.net/json_decode">json_decode</a></td>
<td>48.42 %</td>
<td>17.39</td>
</tr>
<tr>
<td>36</td>
<td><a href="http://php.net/header">header</a></td>
<td>48.16 %</td>
<td>59.71</td>
</tr>
<tr>
<td>37</td>
<td><a href="http://php.net/strtoupper">strtoupper</a></td>
<td>47.80 %</td>
<td>30.95</td>
</tr>
<tr>
<td>38</td>
<td><a href="http://php.net/array_values">array_values</a></td>
<td>47.24 %</td>
<td>17.27</td>
</tr>
<tr>
<td>39</td>
<td><a href="http://php.net/md5">md5</a></td>
<td>46.88 %</td>
<td>23.74</td>
</tr>
<tr>
<td>40</td>
<td><a href="http://php.net/method_exists">method_exists</a></td>
<td>46.73 %</td>
<td>19.05</td>
</tr>
<tr>
<td>41</td>
<td><a href="http://php.net/file_put_contents">file_put_contents</a></td>
<td>46.68 %</td>
<td>12.49</td>
</tr>
<tr>
<td>42</td>
<td><a href="http://php.net/rtrim">rtrim</a></td>
<td>45.91 %</td>
<td>18.08</td>
</tr>
<tr>
<td>43</td>
<td><a href="http://php.net/array_pop">array_pop</a></td>
<td>45.51 %</td>
<td>20.60</td>
</tr>
<tr>
<td>44</td>
<td><a href="http://php.net/unlink">unlink</a></td>
<td>44.59 %</td>
<td>23.55</td>
</tr>
<tr>
<td>45</td>
<td><a href="http://php.net/basename">basename</a></td>
<td>44.59 %</td>
<td>27.23</td>
</tr>
<tr>
<td>46</td>
<td><a href="http://php.net/realpath">realpath</a></td>
<td>44.08 %</td>
<td>15.90</td>
</tr>
<tr>
<td>47</td>
<td><a href="http://php.net/call_user_func">call_user_func</a></td>
<td>43.97 %</td>
<td>16.41</td>
</tr>
<tr>
<td>48</td>
<td><a href="http://php.net/call_user_func_array">call_user_func_array</a></td>
<td>43.92 %</td>
<td>18.40</td>
</tr>
<tr>
<td>49</td>
<td><a href="http://php.net/fopen">fopen</a></td>
<td>43.77 %</td>
<td>25.61</td>
</tr>
<tr>
<td>50</td>
<td><a href="http://php.net/microtime">microtime</a></td>
<td>43.46 %</td>
<td>14.41</td>
</tr>
<tr>
<td>51</td>
<td><a href="http://php.net/fclose">fclose</a></td>
<td>42.85 %</td>
<td>28.36</td>
</tr>
<tr>
<td>52</td>
<td><a href="http://php.net/is_int">is_int</a></td>
<td>42.75 %</td>
<td>15.78</td>
</tr>
<tr>
<td>53</td>
<td><a href="http://php.net/is_file">is_file</a></td>
<td>42.08 %</td>
<td>20.52</td>
</tr>
<tr>
<td>54</td>
<td><a href="http://php.net/array_slice">array_slice</a></td>
<td>41.83 %</td>
<td>13.20</td>
</tr>
<tr>
<td>55</td>
<td><a href="http://php.net/preg_match_all">preg_match_all</a></td>
<td>40.55 %</td>
<td>14.66</td>
</tr>
<tr>
<td>56</td>
<td><a href="http://php.net/ucfirst">ucfirst</a></td>
<td>40.25 %</td>
<td>17.02</td>
</tr>
<tr>
<td>57</td>
<td><a href="http://php.net/intval">intval</a></td>
<td>40.19 %</td>
<td>88.13</td>
</tr>
<tr>
<td>58</td>
<td><a href="http://php.net/str_repeat">str_repeat</a></td>
<td>40.14 %</td>
<td>19.51</td>
</tr>
<tr>
<td>59</td>
<td><a href="http://php.net/serialize">serialize</a></td>
<td>40.14 %</td>
<td>22.05</td>
</tr>
<tr>
<td>60</td>
<td><a href="http://php.net/array_filter">array_filter</a></td>
<td>39.99 %</td>
<td>13.87</td>
</tr>
<tr>
<td>61</td>
<td><a href="http://php.net/mkdir">mkdir</a></td>
<td>39.79 %</td>
<td>11.17</td>
</tr>
<tr>
<td>62</td>
<td><a href="http://php.net/is_callable">is_callable</a></td>
<td>39.43 %</td>
<td>11.94</td>
</tr>
<tr>
<td>63</td>
<td><a href="http://php.net/ltrim">ltrim</a></td>
<td>39.17 %</td>
<td>10.90</td>
</tr>
<tr>
<td>64</td>
<td><a href="http://php.net/ob_start">ob_start</a></td>
<td>39.12 %</td>
<td>13.26</td>
</tr>
<tr>
<td>65</td>
<td><a href="http://php.net/round">round</a></td>
<td>39.07 %</td>
<td>28.56</td>
</tr>
<tr>
<td>66</td>
<td><a href="http://php.net/fwrite">fwrite</a></td>
<td>38.97 %</td>
<td>23.39</td>
</tr>
<tr>
<td>67</td>
<td><a href="http://php.net/array_unique">array_unique</a></td>
<td>38.87 %</td>
<td>15.96</td>
</tr>
<tr>
<td>68</td>
<td><a href="http://php.net/array_search">array_search</a></td>
<td>38.82 %</td>
<td>14.19</td>
</tr>
<tr>
<td>69</td>
<td><a href="http://php.net/reset">reset</a></td>
<td>38.71 %</td>
<td>20.79</td>
</tr>
<tr>
<td>70</td>
<td><a href="http://php.net/array_unshift">array_unshift</a></td>
<td>38.10 %</td>
<td>10.32</td>
</tr>
<tr>
<td>71</td>
<td><a href="http://php.net/parse_url">parse_url</a></td>
<td>37.90 %</td>
<td>9.61</td>
</tr>
<tr>
<td>72</td>
<td><a href="http://php.net/func_get_args">func_get_args</a></td>
<td>37.79 %</td>
<td>28.33</td>
</tr>
<tr>
<td>73</td>
<td><a href="http://php.net/end">end</a></td>
<td>37.49 %</td>
<td>12.70</td>
</tr>
<tr>
<td>74</td>
<td><a href="http://php.net/base64_encode">base64_encode</a></td>
<td>37.39 %</td>
<td>14.15</td>
</tr>
<tr>
<td>75</td>
<td><a href="http://php.net/unserialize">unserialize</a></td>
<td>37.18 %</td>
<td>18.35</td>
</tr>
<tr>
<td>76</td>
<td><a href="http://php.net/max">max</a></td>
<td>36.98 %</td>
<td>22.88</td>
</tr>
<tr>
<td>77</td>
<td><a href="http://php.net/preg_split">preg_split</a></td>
<td>36.98 %</td>
<td>13.27</td>
</tr>
<tr>
<td>78</td>
<td><a href="http://php.net/gettype">gettype</a></td>
<td>36.93 %</td>
<td>16.16</td>
</tr>
<tr>
<td>79</td>
<td><a href="http://php.net/strrpos">strrpos</a></td>
<td>36.67 %</td>
<td>11.95</td>
</tr>
<tr>
<td>80</td>
<td><a href="http://php.net/version_compare">version_compare</a></td>
<td>36.67 %</td>
<td>14.87</td>
</tr>
<tr>
<td>81</td>
<td><a href="http://php.net/array_push">array_push</a></td>
<td>36.67 %</td>
<td>26.18</td>
</tr>
<tr>
<td>82</td>
<td><a href="http://php.net/floor">floor</a></td>
<td>36.11 %</td>
<td>18.78</td>
</tr>
<tr>
<td>83</td>
<td><a href="http://php.net/strtotime">strtotime</a></td>
<td>36.01 %</td>
<td>27.94</td>
</tr>
<tr>
<td>84</td>
<td><a href="http://php.net/htmlspecialchars">htmlspecialchars</a></td>
<td>35.96 %</td>
<td>51.08</td>
</tr>
<tr>
<td>85</td>
<td><a href="http://php.net/ini_get">ini_get</a></td>
<td>35.85 %</td>
<td>19.25</td>
</tr>
<tr>
<td>86</td>
<td><a href="http://php.net/ini_set">ini_set</a></td>
<td>35.60 %</td>
<td>14.49</td>
</tr>
<tr>
<td>87</td>
<td><a href="http://php.net/chr">chr</a></td>
<td>35.34 %</td>
<td>186.97</td>
</tr>
<tr>
<td>88</td>
<td><a href="http://php.net/extension_loaded">extension_loaded</a></td>
<td>35.29 %</td>
<td>14.17</td>
</tr>
<tr>
<td>89</td>
<td><a href="http://php.net/is_bool">is_bool</a></td>
<td>35.24 %</td>
<td>11.44</td>
</tr>
<tr>
<td>90</td>
<td><a href="http://php.net/ksort">ksort</a></td>
<td>34.98 %</td>
<td>10.82</td>
</tr>
<tr>
<td>91</td>
<td><a href="http://php.net/array_reverse">array_reverse</a></td>
<td>34.93 %</td>
<td>8.27</td>
</tr>
<tr>
<td>92</td>
<td><a href="http://php.net/ord">ord</a></td>
<td>34.73 %</td>
<td>53.17</td>
</tr>
<tr>
<td>93</td>
<td><a href="http://php.net/uniqid">uniqid</a></td>
<td>34.68 %</td>
<td>9.83</td>
</tr>
<tr>
<td>94</td>
<td><a href="http://php.net/strtr">strtr</a></td>
<td>34.47 %</td>
<td>12.90</td>
</tr>
<tr>
<td>95</td>
<td><a href="http://php.net/array_diff">array_diff</a></td>
<td>34.32 %</td>
<td>11.13</td>
</tr>
<tr>
<td>96</td>
<td><a href="http://php.net/error_reporting">error_reporting</a></td>
<td>34.17 %</td>
<td>8.99</td>
</tr>
<tr>
<td>97</td>
<td><a href="http://php.net/ceil">ceil</a></td>
<td>33.35 %</td>
<td>11.99</td>
</tr>
<tr>
<td>98</td>
<td><a href="http://php.net/urlencode">urlencode</a></td>
<td>33.30 %</td>
<td>29.63</td>
</tr>
<tr>
<td>99</td>
<td><a href="http://php.net/min">min</a></td>
<td>32.69 %</td>
<td>18.31</td>
</tr>
<tr>
<td>100</td>
<td><a href="http://php.net/print_r">print_r</a></td>
<td>32.64 %</td>
<td>14.12</td>
</tr>
</tbody>
</table>


If you are learning PHP, it is a good idea to review the 100 functions ranked here : they are the features you’ll find the most often when landing on a coding team. They are not the only ones, but you’ll be less surprised when meeting them.


## TOP 100 PHP Functions 视频解说

可以上这位油管的阿婆主的视频空间 [Clever Techie](https://www.youtube.com/channel/UC1WxZFhq56xs1oxXH-XveSQ/videos) 去看看. 他是分了十期做的: 

1. [Top 100 PHP Functions ( 1 - 10 ) - Learn PHP Programming](https://www.youtube.com/watch?v=t9FrpTZm1ds)
2. [TOP 100 PHP Functions ( 11 - 20 ) - PHP Tutorial](https://www.youtube.com/watch?v=rQxnnWg4XqQ)
3. [Top 100 PHP Functions ( 21 - 30 ) - Learn PHP](https://www.youtube.com/watch?v=3in01NvqNW8)
4. [TOP 100 PHP Functions ( 31 - 40 ) - Learn PHP Programming](https://www.youtube.com/watch?v=wP9EvXIJ6Ms)
5. [Top 100 PHP Functions ( 41 - 50 ) - PHP Tutorial](https://www.youtube.com/watch?v=vKhKddOGw-Y)
6. [TOP 100 PHP Functions ( 51 - 60 ) - Learn PHP](https://www.youtube.com/watch?v=-jiMnIwtcuk)
7. [TOP 100 PHP Functions ( 61 - 70 ) - Learn PHP Programming](https://www.youtube.com/watch?v=D6pxBeBa4rk)
8. [TOP 100 PHP Functions ( 71 - 80 ) - PHP Tutorial](https://www.youtube.com/watch?v=n6dqC8kRPuc)
9. [TOP 100 PHP Functions ( 81 - 90 ) - PHP Functions Tutorial](https://www.youtube.com/watch?v=v9DWfPyJg3w)
10. [TOP 100 PHP Functions ( 91 - 100 ) - Learn PHP](https://www.youtube.com/watch?v=VX0o83a_TrY)


PS: 原文在 `TOP 100 PHP Functions (xx - xxx)` 和 `Learn PHP Programming`/`PHP Tutorial` 中间是拿 `|` 连的, 而我本地预览没啥事儿, 但是扔网上就给解析成表格了, 所以后来用 `-` 来分隔了...