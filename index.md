---
layout: page
---

The quiz questions are built using an include with parameters.  The template expects 3 parameters:

- question - the text for the question
- choices - an array of options for the question, presented in the order given
- answer - the position of the correct answer in the choices array
- feedback (optional) - the array of feedback options, must match the order of the choices array

It is easiest to use variables to hold the parameter values, then pass the variables into the include.  The variables can be setup in the page YML or as liquid variables (shown below).

{% highlight liquid %}
{% raw %}
  {% assign q1_text = "This is an awesome template!" %}
  {% assign q1_choices = "True, False" | split: ', ' %}
  {% assign q1_feedbacks = "Correct!  This is an awesome template., How can you say that?!" | split: ', ' %}
  {% assign q1_correct = 0 %}
  {% include mc-quiz.html text=q1_text choices=q1_choices answer=q1_correct feedback=q1_feedbacks %}
{% endraw %}
{% endhighlight %}

<hr>
<br>
{% assign q1-text = "This is an awesome template!" %}
{% assign q1-choices = "True, False" | split: ', ' %}
{% assign q1_feedbacks = "Correct!  This is an awesome template., How can you say that?!" | split: ', ' %}
{% assign q1-correct = 0 %}
{% include mc-quiz.html text=q1-text choices=q1-choices answer=q1-correct feedback=q1_feedbacks %}
<br>
<hr>
<br><br>
Clearly some CSS is needed to pretty this up... but the solution checking and feedback showing is handled through inline JavaScript.