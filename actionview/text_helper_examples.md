Run options: --seed 8029

# Running:



#simple_format_should_be_html_safe
1. `ActionView::Helpers::TextHelper#simple_format(["<b> test with html tags </b>"])`
`<p><b> test with html tags </b></p>`
.

#simple_format_should_not_sanitize_input_when_sanitize_option_is_false
1. `ActionView::Helpers::TextHelper#simple_format(["<b> test with unsafe string </b><script>code!</script>", {}, {:sanitize=>false}])`
`<p><b> test with unsafe string </b><script>code!</script></p>`
.

#cycle_with_no_arguments
.

#cycle_class
.

#truncate_with_options_hash
1. `ActionView::Helpers::TextHelper#truncate(["This is a string that will go longer then the default truncate length of 30", {:omission=>"[...]"}])`
`This is a string that wil[...]`
1. `ActionView::Helpers::TextHelper#truncate(["Hello World!", {:length=>10}])`
`Hello W...`
1. `ActionView::Helpers::TextHelper#truncate(["Hello World!", {:omission=>"[...]", :length=>10}])`
`Hello[...]`
1. `ActionView::Helpers::TextHelper#truncate(["Hello Big World!", {:omission=>"[...]", :length=>13, :separator=>" "}])`
`Hello[...]`
1. `ActionView::Helpers::TextHelper#truncate(["Hello Big World!", {:omission=>"[...]", :length=>14, :separator=>" "}])`
`Hello Big[...]`
1. `ActionView::Helpers::TextHelper#truncate(["Hello Big World!", {:omission=>"[...]", :length=>15, :separator=>" "}])`
`Hello Big[...]`
.

#excerpt
1. `ActionView::Helpers::TextHelper#excerpt(["This is a beautiful morning", "beautiful", {:radius=>5}])`
`...is a beautiful morn...`
1. `ActionView::Helpers::TextHelper#excerpt(["This is a beautiful morning", "this", {:radius=>5}])`
`This is a...`
1. `ActionView::Helpers::TextHelper#excerpt(["This is a beautiful morning", "morning", {:radius=>5}])`
`...iful morning`
1. `ActionView::Helpers::TextHelper#excerpt(["This is a beautiful morning", "day"])`
``
.

#current_cycle_with_named_cycles
1. `ActionView::Helpers::TextHelper#cycle(["red", "blue", {:name=>"colors"}])`
`red`
1. `ActionView::Helpers::TextHelper#current_cycle(["colors"])`
`red`
1. `ActionView::Helpers::TextHelper#cycle(["red", "blue", {:name=>"colors"}])`
`blue`
1. `ActionView::Helpers::TextHelper#current_cycle(["colors"])`
`blue`
1. `ActionView::Helpers::TextHelper#cycle(["red", "blue", {:name=>"colors"}])`
`red`
1. `ActionView::Helpers::TextHelper#current_cycle(["colors"])`
`red`
.

#truncate_with_block_should_escape_the_input
1. `ActionView::Helpers::TextHelper#truncate(["<script>code!</script>Here's a long test and I need a continue to read link", {:length=>27}])`
`&lt;script&gt;code!&lt;/script&gt;He...<a href="#">Continue</a>`
.

#simple_format_does_not_modify_the_options_hash
1. `ActionView::Helpers::TextHelper#simple_format(["some text", {}, {:wrapper_tag=>:div, :sanitize=>false}])`
`<div>some text</div>`
.

#cycle
1. `ActionView::Helpers::TextHelper#cycle(["one", 2, "3"])`
`one`
1. `ActionView::Helpers::TextHelper#cycle(["one", 2, "3"])`
`2`
1. `ActionView::Helpers::TextHelper#cycle(["one", 2, "3"])`
`3`
1. `ActionView::Helpers::TextHelper#cycle(["one", 2, "3"])`
`one`
1. `ActionView::Helpers::TextHelper#cycle(["one", 2, "3"])`
`2`
1. `ActionView::Helpers::TextHelper#cycle(["one", 2, "3"])`
`3`
.

#truncate_with_block_should_not_escape_the_input_with_escape_false
1. `ActionView::Helpers::TextHelper#truncate(["<script>code!</script>Here's a long test and I need a continue to read link", {:length=>27, :escape=>false}])`
`<script>code!</script>He...<a href="#">Continue</a>`
.

#reset_cycle
1. `ActionView::Helpers::TextHelper#cycle([1, 2, 3])`
`1`
1. `ActionView::Helpers::TextHelper#cycle([1, 2, 3])`
`2`
1. `ActionView::Helpers::TextHelper#reset_cycle([])`
`0`
1. `ActionView::Helpers::TextHelper#cycle([1, 2, 3])`
`1`
.

#highlight_accepts_regexp
1. `ActionView::Helpers::TextHelper#highlight(["This day was challenging for judge Allen and his colleagues.", /\ballen\b/i])`
`This day was challenging for judge <mark>Allen</mark> and his colleagues.`
.

#truncate_with_block_with_escape_false_should_be_html_safe
1. `ActionView::Helpers::TextHelper#truncate(["<script>code!</script>Here's a long test and I need a continue to read link", {:length=>27, :escape=>false}])`
`<script>code!</script>He...<a href="#">Continue</a>`
.

#truncate_should_escape_the_input
1. `ActionView::Helpers::TextHelper#truncate(["Hello <script>code!</script>World!!", {:length=>12}])`
`Hello &lt;sc...`
.

#word_wrap_with_custom_break_sequence
1. `ActionView::Helpers::TextHelper#word_wrap(["1234567890 1234567890 1234567890 ", {:line_width=>2, :break_sequence=>"\r\n"}])`
`1234567890
1234567890
1234567890`
.

#word_wrap_does_not_modify_the_options_hash
1. `ActionView::Helpers::TextHelper#word_wrap(["some text", {:line_width=>15}])`
`some text`
.

#cycle_with_array
1. `ActionView::Helpers::TextHelper#cycle([[1, 2, 3]])`
`1`
1. `ActionView::Helpers::TextHelper#cycle([[1, 2, 3]])`
`2`
1. `ActionView::Helpers::TextHelper#cycle([[1, 2, 3]])`
`3`
.

#cycle_resets_with_new_values
1. `ActionView::Helpers::TextHelper#cycle(["even", "odd"])`
`even`
1. `ActionView::Helpers::TextHelper#cycle(["even", "odd"])`
`odd`
1. `ActionView::Helpers::TextHelper#cycle(["even", "odd"])`
`even`
1. `ActionView::Helpers::TextHelper#cycle([1, 2, 3])`
`1`
1. `ActionView::Helpers::TextHelper#cycle([1, 2, 3])`
`2`
1. `ActionView::Helpers::TextHelper#cycle([1, 2, 3])`
`3`
1. `ActionView::Helpers::TextHelper#cycle([1, 2, 3])`
`1`
.

#truncate_with_link_options
1. `ActionView::Helpers::TextHelper#truncate(["Here is a long test and I need a continue to read link", {:length=>27}])`
`Here is a long test and ...<a href="#">Continue</a>`
.

#current_cycle_with_more_than_two_names
1. `ActionView::Helpers::TextHelper#cycle([1, 2, 3])`
`1`
1. `ActionView::Helpers::TextHelper#current_cycle([])`
`1`
1. `ActionView::Helpers::TextHelper#cycle([1, 2, 3])`
`2`
1. `ActionView::Helpers::TextHelper#current_cycle([])`
`2`
1. `ActionView::Helpers::TextHelper#cycle([1, 2, 3])`
`3`
1. `ActionView::Helpers::TextHelper#current_cycle([])`
`3`
1. `ActionView::Helpers::TextHelper#cycle([1, 2, 3])`
`1`
1. `ActionView::Helpers::TextHelper#current_cycle([])`
`1`
.

#simple_format_should_not_change_the_text_passed
1. `ActionView::Helpers::TextHelper#simple_format(["<b>Ok</b><script>code!</script>"])`
`<p><b>Ok</b>code!</p>`
.

#truncate_should_not_escape_the_input_with_escape_false
1. `ActionView::Helpers::TextHelper#truncate(["Hello <script>code!</script>World!!", {:length=>12, :escape=>false}])`
`Hello <sc...`
.

#simple_format_with_custom_wrapper_and_multi_line_breaks
1. `ActionView::Helpers::TextHelper#simple_format(["We want to put a wrapper...\n\n...right there.", {}, {:wrapper_tag=>"div"}])`
`<div>We want to put a wrapper...</div>

<div>...right there.</div>`
.

#truncate_with_block_should_escape_the_block
1. `ActionView::Helpers::TextHelper#truncate(["Here is a long test and I need a continue to read link", {:length=>27}])`
`Here is a long test and ...&lt;script&gt;alert(&#39;foo&#39;);&lt;/script&gt;`
.

#highlight_should_sanitize_input
1. `ActionView::Helpers::TextHelper#highlight(["This is a beautiful morning<script>code!</script>", "beautiful"])`
`This is a <mark>beautiful</mark> morningcode!`
.

#cycle_no_instance_variable_clashes
1. `ActionView::Helpers::TextHelper#cycle(["red", "blue"])`
`red`
1. `ActionView::Helpers::TextHelper#cycle(["red", "blue"])`
`blue`
1. `ActionView::Helpers::TextHelper#cycle(["red", "blue"])`
`red`
.

#excerpt_with_omission
1. `ActionView::Helpers::TextHelper#excerpt(["This is a beautiful morning", "beautiful", {:omission=>"[...]", :radius=>5}])`
`[...]is a beautiful morn[...]`
1. `ActionView::Helpers::TextHelper#excerpt(["This is the ultimate supercalifragilisticexpialidoceous very looooooooooooooooooong looooooooooooong beautiful morning with amazing sunshine and awesome temperatures. So what are you gonna do about it?", "very", {:omission=>"[...]"}])`
`This is the ultimate supercalifragilisticexpialidoceous very looooooooooooooooooong looooooooooooong beautiful morning with amazing sunshine and awesome tempera[...]`
.

#excerpt_in_borderline_cases
1. `ActionView::Helpers::TextHelper#excerpt(["", "", {:radius=>0}])`
``
1. `ActionView::Helpers::TextHelper#excerpt(["a", "a", {:radius=>0}])`
`a`
1. `ActionView::Helpers::TextHelper#excerpt(["abc", "b", {:radius=>0}])`
`...b...`
1. `ActionView::Helpers::TextHelper#excerpt(["abc", "b", {:radius=>1}])`
`abc`
1. `ActionView::Helpers::TextHelper#excerpt(["abcd", "b", {:radius=>1}])`
`abc...`
1. `ActionView::Helpers::TextHelper#excerpt(["zabc", "b", {:radius=>1}])`
`...abc`
1. `ActionView::Helpers::TextHelper#excerpt(["zabcd", "b", {:radius=>1}])`
`...abc...`
1. `ActionView::Helpers::TextHelper#excerpt(["zabcd", "b", {:radius=>2}])`
`zabcd`
1. `ActionView::Helpers::TextHelper#excerpt(["  zabcd  ", "b", {:radius=>4}])`
`zabcd`
1. `ActionView::Helpers::TextHelper#excerpt(["z  abc  d", "b", {:radius=>1}])`
`...abc...`
.

#highlight_should_be_html_safe
1. `ActionView::Helpers::TextHelper#highlight(["This is a beautiful morning", "beautiful"])`
`This is a <mark>beautiful</mark> morning`
.

#simple_format
1. `ActionView::Helpers::TextHelper#simple_format([nil])`
`<p></p>`
1. `ActionView::Helpers::TextHelper#simple_format(["crazy\r\n cross\r platform linebreaks"])`
`<p>crazy
<br /> cross
<br /> platform linebreaks</p>`
1. `ActionView::Helpers::TextHelper#simple_format(["A paragraph\n\nand another one!"])`
`<p>A paragraph</p>

<p>and another one!</p>`
1. `ActionView::Helpers::TextHelper#simple_format(["A paragraph\n With a newline"])`
`<p>A paragraph
<br /> With a newline</p>`
1. `ActionView::Helpers::TextHelper#simple_format(["A\nB\nC\nD"])`
`<p>A
<br />B
<br />C
<br />D</p>`
1. `ActionView::Helpers::TextHelper#simple_format(["A\r\n  \nB\n\n\r\n\t\nC\nD"])`
`<p>A
<br />  
<br />B</p>

<p>	
<br />C
<br />D</p>`
1. `ActionView::Helpers::TextHelper#simple_format(["This is a classy test", {:class=>"test"}])`
`<p class="test">This is a classy test</p>`
1. `ActionView::Helpers::TextHelper#simple_format(["para 1\n\npara 2", {:class=>"test"}])`
`<p class="test">para 1</p>

<p class="test">para 2</p>`
.

#truncate_should_be_html_safe
1. `ActionView::Helpers::TextHelper#truncate(["Hello World!", {:length=>12}])`
`Hello World!`
.

#truncate_multibyte
1. `ActionView::Helpers::TextHelper#truncate(["아리랑 아리 아라리오", {:length=>10}])`
`아리랑 아리 ...`
.

#highlight_pending
1. `ActionView::Helpers::TextHelper#highlight(["   ", "blank text is returned verbatim"])`
`   `
.

#simple_format_with_custom_wrapper
1. `ActionView::Helpers::TextHelper#simple_format([nil, {}, {:wrapper_tag=>"div"}])`
`<div></div>`
.

#simple_format_should_sanitize_input_when_sanitize_option_is_not_false
1. `ActionView::Helpers::TextHelper#simple_format(["<b> test with unsafe string </b><script>code!</script>"])`
`<p><b> test with unsafe string </b>code!</p>`
.

#highlight_should_return_blank_string_for_nil
1. `ActionView::Helpers::TextHelper#highlight([nil, "blank string is returned for nil"])`
``
.

#word_wrap_with_extra_newlines
1. `ActionView::Helpers::TextHelper#word_wrap(["my very very very long string\n\nwith another line", {:line_width=>15}])`
`my very very
very long
string

with another
line`
.

#simple_format_included_in_isolation
1. `ActionView::Helpers::TextHelper#simple_format(["<b> test with html tags </b>"])`
`<p><b> test with html tags </b></p>`
.

#highlight_with_regexp
1. `ActionView::Helpers::TextHelper#highlight(["This is a beautiful! morning", "beautiful!"])`
`This is a <mark>beautiful!</mark> morning`
1. `ActionView::Helpers::TextHelper#highlight(["This is a beautiful! morning", "beautiful! morning"])`
`This is a <mark>beautiful! morning</mark>`
1. `ActionView::Helpers::TextHelper#highlight(["This is a beautiful? morning", "beautiful? morning"])`
`This is a <mark>beautiful? morning</mark>`
.

#reset_unknown_cycle
1. `ActionView::Helpers::TextHelper#reset_cycle(["colors"])`
``
.

#simple_format_does_not_modify_the_html_options_hash
1. `ActionView::Helpers::TextHelper#simple_format(["some text", {:class=>"foobar"}])`
`<p class="foobar">some text</p>`
.

#highlight_with_html
1. `ActionView::Helpers::TextHelper#highlight(["<p>This is a beautiful morning, but also a beautiful day</p>", "beautiful"])`
`<p>This is a <mark>beautiful</mark> morning, but also a <mark>beautiful</mark> day</p>`
1. `ActionView::Helpers::TextHelper#highlight(["<p>This is a <em>beautiful</em> morning, but also a beautiful day</p>", "beautiful"])`
`<p>This is a <em><mark>beautiful</mark></em> morning, but also a <mark>beautiful</mark> day</p>`
1. `ActionView::Helpers::TextHelper#highlight(["<p>This is a <em class=\"error\">beautiful</em> morning, but also a beautiful <span class=\"last\">day</span></p>", "beautiful"])`
`<p>This is a <em class="error"><mark>beautiful</mark></em> morning, but also a <mark>beautiful</mark> <span class="last">day</span></p>`
1. `ActionView::Helpers::TextHelper#highlight(["<p class=\"beautiful\">This is a beautiful morning, but also a beautiful day</p>", "beautiful"])`
`<p class="beautiful">This is a <mark>beautiful</mark> morning, but also a <mark>beautiful</mark> day</p>`
1. `ActionView::Helpers::TextHelper#highlight(["<p>This is a beautiful <a href=\"http://example.com/beautiful#top?what=beautiful%20morning&when=now+then\">morning</a>, but also a beautiful day</p>", "beautiful"])`
`<p>This is a <mark>beautiful</mark> <a href="http://example.com/beautiful#top?what=beautiful%20morning&amp;when=now+then">morning</a>, but also a <mark>beautiful</mark> day</p>`
1. `ActionView::Helpers::TextHelper#highlight(["<div>abc div</div>", "div", {:highlighter=>"<b>\\1</b>"}])`
`<div>abc <b>div</b></div>`
.

#highlight_with_block
1. `ActionView::Helpers::TextHelper#highlight(["one two three", ["one", "two", "three"]])`
`<b>one</b> <b>two</b> <b>three</b>`
.

#excerpt_with_separator
1. `ActionView::Helpers::TextHelper#excerpt(["This is a very beautiful morning", "very", {:separator=>" ", :radius=>1}])`
`...a very beautiful...`
1. `ActionView::Helpers::TextHelper#excerpt(["This is a very beautiful morning", "this", {:separator=>" ", :radius=>1}])`
`This is...`
1. `ActionView::Helpers::TextHelper#excerpt(["This is a very beautiful morning", "morning", {:separator=>" ", :radius=>1}])`
`...beautiful morning`
1. `ActionView::Helpers::TextHelper#excerpt(["my very\nvery\nvery long\nstring", "long", {:separator=>"\n", :radius=>0}])`
`...very long...`
1. `ActionView::Helpers::TextHelper#excerpt(["my very\nvery\nvery long\nstring", "long", {:separator=>"\n", :radius=>1}])`
`...very
very long
string`
1. `ActionView::Helpers::TextHelper#excerpt(["This is a beautiful morning", "a"])`
`This is a beautiful morning`
1. `ActionView::Helpers::TextHelper#excerpt(["This is a beautiful morning", "a", {:separator=>nil}])`
`This is a beautiful morning`
.

#cycle_class_with_no_arguments
.

#truncate_should_use_default_length_of_30
1. `ActionView::Helpers::TextHelper#truncate(["This is a string that will go longer then the default truncate length of 30"])`
`This is a string that will ...`
.

#simple_format_should_sanitize_input_when_sanitize_option_is_true
1. `ActionView::Helpers::TextHelper#simple_format(["<b> test with unsafe string </b><script>code!</script>", {}, {:sanitize=>true}])`
`<p><b> test with unsafe string </b>code!</p>`
.

#current_cycle_with_default_name
1. `ActionView::Helpers::TextHelper#cycle(["even", "odd"])`
`even`
1. `ActionView::Helpers::TextHelper#current_cycle([])`
`even`
1. `ActionView::Helpers::TextHelper#cycle(["even", "odd"])`
`odd`
1. `ActionView::Helpers::TextHelper#current_cycle([])`
`odd`
1. `ActionView::Helpers::TextHelper#cycle(["even", "odd"])`
`even`
1. `ActionView::Helpers::TextHelper#current_cycle([])`
`even`
.

#excerpt_with_regex
1. `ActionView::Helpers::TextHelper#excerpt(["This is a beautiful! morning", "beautiful", {:radius=>5}])`
`...is a beautiful! mor...`
1. `ActionView::Helpers::TextHelper#excerpt(["This is a beautiful? morning", "beautiful", {:radius=>5}])`
`...is a beautiful? mor...`
1. `ActionView::Helpers::TextHelper#excerpt(["This is a beautiful? morning", /\bbeau\w*\b/i, {:radius=>5}])`
`...is a beautiful? mor...`
1. `ActionView::Helpers::TextHelper#excerpt(["This is a beautiful? morning", /\b(beau\w*)\b/i, {:radius=>5}])`
`...is a beautiful? mor...`
1. `ActionView::Helpers::TextHelper#excerpt(["This day was challenging for judge Allen and his colleagues.", /\ballen\b/i, {:radius=>5}])`
`...udge Allen and...`
1. `ActionView::Helpers::TextHelper#excerpt(["This day was challenging for judge Allen and his colleagues.", /\ballen\b/i, {:radius=>1, :separator=>" "}])`
`...judge Allen and...`
1. `ActionView::Helpers::TextHelper#excerpt(["This day was challenging for judge Allen and his colleagues.", /\b(\w*allen\w*)\b/i, {:radius=>5}])`
`...was challenging for...`
.

#localized_pluralization
1. `ActionView::Helpers::TextHelper#pluralize([1, "region"])`
`1 region`
1. `ActionView::Helpers::TextHelper#pluralize([2, "region"])`
`2 regionen`
1. `ActionView::Helpers::TextHelper#pluralize([2, "region", {:locale=>:en}])`
`2 regions`
.

#highlight_does_not_modify_the_options_hash
1. `ActionView::Helpers::TextHelper#highlight(["<div>abc div</div>", "div", {:highlighter=>"<b>\\1</b>", :sanitize=>false}])`
`<div>abc <b>div</b></div>`
.

#truncate
1. `ActionView::Helpers::TextHelper#truncate(["Hello World!", {:length=>12}])`
`Hello World!`
1. `ActionView::Helpers::TextHelper#truncate(["Hello World!!", {:length=>12}])`
`Hello Wor...`
.

#named_cycles
1. `ActionView::Helpers::TextHelper#cycle([1, 2, 3, {:name=>"numbers"}])`
`1`
1. `ActionView::Helpers::TextHelper#cycle(["red", "blue", {:name=>"colors"}])`
`red`
1. `ActionView::Helpers::TextHelper#cycle([1, 2, 3, {:name=>"numbers"}])`
`2`
1. `ActionView::Helpers::TextHelper#cycle(["red", "blue", {:name=>"colors"}])`
`blue`
1. `ActionView::Helpers::TextHelper#cycle([1, 2, 3, {:name=>"numbers"}])`
`3`
1. `ActionView::Helpers::TextHelper#cycle(["red", "blue", {:name=>"colors"}])`
`red`
.

#pluralization
1. `ActionView::Helpers::TextHelper#pluralize([1, "count"])`
`1 count`
1. `ActionView::Helpers::TextHelper#pluralize([2, "count"])`
`2 counts`
1. `ActionView::Helpers::TextHelper#pluralize(["1", "count"])`
`1 count`
1. `ActionView::Helpers::TextHelper#pluralize(["2", "count"])`
`2 counts`
1. `ActionView::Helpers::TextHelper#pluralize(["1,066", "count"])`
`1,066 counts`
1. `ActionView::Helpers::TextHelper#pluralize(["1.25", "count"])`
`1.25 counts`
1. `ActionView::Helpers::TextHelper#pluralize(["1.0", "count"])`
`1.0 count`
1. `ActionView::Helpers::TextHelper#pluralize(["1.00", "count"])`
`1.00 count`
1. `ActionView::Helpers::TextHelper#pluralize([2, "count", "counters"])`
`2 counters`
1. `ActionView::Helpers::TextHelper#pluralize([nil, "count", "counters"])`
`0 counters`
1. `ActionView::Helpers::TextHelper#pluralize([2, "count", {:plural=>"counters"}])`
`2 counters`
1. `ActionView::Helpers::TextHelper#pluralize([nil, "count", {:plural=>"counters"}])`
`0 counters`
1. `ActionView::Helpers::TextHelper#pluralize([2, "person"])`
`2 people`
1. `ActionView::Helpers::TextHelper#pluralize([10, "buffalo"])`
`10 buffaloes`
1. `ActionView::Helpers::TextHelper#pluralize([1, "berry"])`
`1 berry`
1. `ActionView::Helpers::TextHelper#pluralize([12, "berry"])`
`12 berries`
.

#excerpt_does_not_modify_the_options_hash
1. `ActionView::Helpers::TextHelper#excerpt(["This is a beautiful morning", "beautiful", {:omission=>"[...]", :radius=>5}])`
`[...]is a beautiful morn[...]`
.

#concat
1. `ActionView::Helpers::TextHelper#concat(["bar"])`
`foobar`
.

#truncate_with_block_should_be_html_safe
1. `ActionView::Helpers::TextHelper#truncate(["Here's a long test and I need a continue to read link", {:length=>27}])`
`Here&#39;s a long test and I...<a href="#">Continue</a>`
.

#highlight_with_multiple_phrases_in_one_pass
1. `ActionView::Helpers::TextHelper#highlight(["wow em", ["wow", "em"], {:highlighter=>"<em>\\1</em>"}])`
`<em>wow</em> <em>em</em>`
.

#highlight_should_not_sanitize_if_sanitize_option_if_false
1. `ActionView::Helpers::TextHelper#highlight(["This is a beautiful morning<script>code!</script>", "beautiful", {:sanitize=>false}])`
`This is a <mark>beautiful</mark> morning<script>code!</script>`
.

#truncate_does_not_modify_the_options_hash
1. `ActionView::Helpers::TextHelper#truncate(["some text", {:length=>10}])`
`some text`
.

#highlight
1. `ActionView::Helpers::TextHelper#highlight(["This is a beautiful morning", "beautiful"])`
`This is a <mark>beautiful</mark> morning`
1. `ActionView::Helpers::TextHelper#highlight(["This is a beautiful morning, but also a beautiful day", "beautiful"])`
`This is a <mark>beautiful</mark> morning, but also a <mark>beautiful</mark> day`
1. `ActionView::Helpers::TextHelper#highlight(["This is a beautiful morning, but also a beautiful day", "beautiful", {:highlighter=>"<b>\\1</b>"}])`
`This is a <b>beautiful</b> morning, but also a <b>beautiful</b> day`
1. `ActionView::Helpers::TextHelper#highlight(["This text is not changed because we supplied an empty phrase", nil])`
`This text is not changed because we supplied an empty phrase`
.

#current_cycle_safe_call
1. `ActionView::Helpers::TextHelper#current_cycle([])`
``
1. `ActionView::Helpers::TextHelper#current_cycle(["colors"])`
``
.

#default_named_cycle
1. `ActionView::Helpers::TextHelper#cycle([1, 2, 3])`
`1`
1. `ActionView::Helpers::TextHelper#cycle([1, 2, 3, {:name=>"default"}])`
`2`
1. `ActionView::Helpers::TextHelper#cycle([1, 2, 3])`
`3`
.

#word_wrap
1. `ActionView::Helpers::TextHelper#word_wrap(["my very very very long string", {:line_width=>15}])`
`my very very
very long
string`
.

#excerpt_with_utf8
1. `ActionView::Helpers::TextHelper#excerpt(["That's why eﬃciency could not be helped", "could", {:radius=>8}])`
`...ﬃciency could not be...`
.

#truncate_with_escape_false_should_be_html_safe
1. `ActionView::Helpers::TextHelper#truncate(["Hello <script>code!</script>World!!", {:length=>12, :escape=>false}])`
`Hello <sc...`
.

#excerpt_should_not_be_html_safe
1. `ActionView::Helpers::TextHelper#excerpt(["This is a beautiful! morning", "beautiful", {:radius=>5}])`
`...is a beautiful! mor...`
.

#reset_named_cycle
1. `ActionView::Helpers::TextHelper#cycle([1, 2, 3, {:name=>"numbers"}])`
`1`
1. `ActionView::Helpers::TextHelper#cycle(["red", "blue", {:name=>"colors"}])`
`red`
1. `ActionView::Helpers::TextHelper#reset_cycle(["numbers"])`
`0`
1. `ActionView::Helpers::TextHelper#cycle([1, 2, 3, {:name=>"numbers"}])`
`1`
1. `ActionView::Helpers::TextHelper#cycle(["red", "blue", {:name=>"colors"}])`
`blue`
1. `ActionView::Helpers::TextHelper#cycle([1, 2, 3, {:name=>"numbers"}])`
`2`
1. `ActionView::Helpers::TextHelper#cycle(["red", "blue", {:name=>"colors"}])`
`red`
.

Finished in 0.056755s, 1215.7519 runs/s, 3083.4288 assertions/s.

69 runs, 175 assertions, 0 failures, 0 errors, 0 skips
