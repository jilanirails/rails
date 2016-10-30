Run options: --seed 60885

# Running:



#form_tag_enforce_utf8_true
1. `ActionView::Helpers::FormTagHelper#utf8_enforcer_tag([])`
`<input name="utf8" type="hidden" value="&#x2713;" />`
1. `ActionView::Helpers::FormTagHelper#form_tag([{}, {:enforce_utf8=>true}])`
`<form action="http://www.example.com" accept-charset="UTF-8" method="post"><input name="utf8" type="hidden" value="&#x2713;" />`
.

#select_tag_id_sanitized
1. `ActionView::Helpers::FormTagHelper#select_tag(["project[1]people", "<option>david</option>"])`
`<select name="project[1]people" id="project_1people">&lt;option&gt;david&lt;/option&gt;</select>`
.

#text_field_tag_with_placeholder_option
1. `ActionView::Helpers::FormTagHelper#text_field_tag(["title", "Hello!", {:placeholder=>"Enter search term..."}])`
`<input type="text" name="title" id="title" value="Hello!" placeholder="Enter search term..." />`
.

#button_tag_with_confirmation
1. `ActionView::Helpers::FormTagHelper#button_tag(["Save", {:type=>"submit", :data=>{:confirm=>"Are you sure?"}}])`
`<button name="button" type="submit" data-confirm="Are you sure?">Save</button>`
.

#empty_submit_tag_with_opt_out
1. `ActionView::Helpers::FormTagHelper#submit_tag(["Save"])`
`<input type="submit" name="commit" value="Save" />`
.

#time_field_tag
1. `ActionView::Helpers::FormTagHelper#text_field_tag(["cell", nil, {:type=>:time}])`
`<input type="time" name="cell" id="cell" />`
1. `ActionView::Helpers::FormTagHelper#time_field_tag(["cell"])`
`<input type="time" name="cell" id="cell" />`
.

#select_tag
1. `ActionView::Helpers::FormTagHelper#select_tag(["people", "<option>david</option>"])`
`<select name="people" id="people"><option>david</option></select>`
.

#form_tag_with_block_and_method_in_erb
1. `ActionView::Helpers::FormTagHelper#utf8_enforcer_tag([])`
`<input name="utf8" type="hidden" value="&#x2713;" />`
1. `ActionView::Helpers::FormTagHelper#form_tag(["http://www.example.com", {:method=>:put}])`
`<form action="http://www.example.com" accept-charset="UTF-8" method="post"><input name="utf8" type="hidden" value="&#x2713;" /><input type="hidden" name="_method" value="put" />Hello world!</form>`
.

#boolean_options
1. `ActionView::Helpers::FormTagHelper#check_box_tag(["admin", 1, true, {"disabled"=>true, :readonly=>"yes"}])`
`<input type="checkbox" name="admin" id="admin" value="1" disabled="disabled" readonly="readonly" checked="checked" />`
1. `ActionView::Helpers::FormTagHelper#check_box_tag(["admin", 1, true, {:disabled=>false, :readonly=>nil}])`
`<input type="checkbox" name="admin" id="admin" value="1" checked="checked" />`
1. `ActionView::Helpers::FormTagHelper#select_tag(["people", "<option>david</option>", {:multiple=>true}])`
`<select name="people[]" id="people" multiple="multiple"><option>david</option></select>`
1. `ActionView::Helpers::FormTagHelper#select_tag(["people[]", "<option>david</option>", {:multiple=>true}])`
`<select name="people[]" id="people_" multiple="multiple"><option>david</option></select>`
1. `ActionView::Helpers::FormTagHelper#select_tag(["people", "<option>david</option>", {:multiple=>nil}])`
`<select name="people" id="people"><option>david</option></select>`
.

#text_field_tag_disabled
1. `ActionView::Helpers::FormTagHelper#text_field_tag(["title", "Hello!", {:disabled=>true}])`
`<input type="text" name="title" id="title" value="Hello!" disabled="disabled" />`
.

#submit_tag_having_data_disable_with_boolean
1. `ActionView::Helpers::FormTagHelper#submit_tag(["Save", {"data-disable-with"=>false, "data-confirm"=>"Are you sure?"}])`
`<input type="submit" name="commit" value="Save" data-confirm="Are you sure?" />`
.

#form_tag_with_method_delete
1. `ActionView::Helpers::FormTagHelper#utf8_enforcer_tag([])`
`<input name="utf8" type="hidden" value="&#x2713;" />`
1. `ActionView::Helpers::FormTagHelper#form_tag([{}, {:method=>:delete}])`
`<form action="http://www.example.com" accept-charset="UTF-8" method="post"><input name="utf8" type="hidden" value="&#x2713;" /><input type="hidden" name="_method" value="delete" />`
.

#image_submit_tag_options_symbolize_keys_side_effects
1. `ActionView::Helpers::FormTagHelper#image_submit_tag(["submit source", {:option=>"random_option"}])`
`<input alt="Submit source" type="image" src="/images/submit source" option="random_option" />`
.

#button_tag_with_data_disable_with_option
1. `ActionView::Helpers::FormTagHelper#button_tag(["Checkout", {:data=>{:disable_with=>"Please wait..."}}])`
`<button name="button" type="submit" data-disable-with="Please wait...">Checkout</button>`
.

#text_field_tag_with_multiple_options
1. `ActionView::Helpers::FormTagHelper#text_field_tag(["title", "Hello!", {:size=>70, :maxlength=>80}])`
`<input type="text" name="title" id="title" value="Hello!" size="70" maxlength="80" />`
.

#text_area_tag_escape_content
1. `ActionView::Helpers::FormTagHelper#text_area_tag(["body", "<b>hello world</b>", {:size=>"20x40"}])`
`<textarea name="body" id="body" cols="20" rows="40">
&lt;b&gt;hello world&lt;/b&gt;</textarea>`
.

#file_field_tag
1. `ActionView::Helpers::FormTagHelper#text_field_tag(["picsplz", nil, {:type=>:file}])`
`<input type="file" name="picsplz" id="picsplz" />`
1. `ActionView::Helpers::FormTagHelper#file_field_tag(["picsplz"])`
`<input type="file" name="picsplz" id="picsplz" />`
.

#check_box_tag
1. `ActionView::Helpers::FormTagHelper#check_box_tag(["admin"])`
`<input type="checkbox" name="admin" id="admin" value="1" />`
.

#label_tag_with_text
1. `ActionView::Helpers::FormTagHelper#label_tag(["title", "My Title"])`
`<label for="title">My Title</label>`
.

#label_tag_with_symbol
1. `ActionView::Helpers::FormTagHelper#label_tag([:title])`
`<label for="title">Title</label>`
.

#label_tag_class_string
1. `ActionView::Helpers::FormTagHelper#label_tag(["title", "My Title", {"class"=>"small_label"}])`
`<label class="small_label" for="title">My Title</label>`
.

#label_tag_with_block
1. `ActionView::Helpers::FormTagHelper#label_tag([])`
`<label>Blocked</label>`
.

#datetime_local_field_tag
1. `ActionView::Helpers::FormTagHelper#text_field_tag(["appointment", nil, {:type=>"datetime-local"}])`
`<input type="datetime-local" name="appointment" id="appointment" />`
1. `ActionView::Helpers::FormTagHelper#datetime_local_field_tag(["appointment"])`
`<input type="datetime-local" name="appointment" id="appointment" />`
.

#form_tag_with_remote_false
1. `ActionView::Helpers::FormTagHelper#utf8_enforcer_tag([])`
`<input name="utf8" type="hidden" value="&#x2713;" />`
1. `ActionView::Helpers::FormTagHelper#form_tag([{}, {:remote=>false}])`
`<form action="http://www.example.com" accept-charset="UTF-8" method="post"><input name="utf8" type="hidden" value="&#x2713;" />`
.

#form_tag_with_method_patch
1. `ActionView::Helpers::FormTagHelper#utf8_enforcer_tag([])`
`<input name="utf8" type="hidden" value="&#x2713;" />`
1. `ActionView::Helpers::FormTagHelper#form_tag([{}, {:method=>:patch}])`
`<form action="http://www.example.com" accept-charset="UTF-8" method="post"><input name="utf8" type="hidden" value="&#x2713;" /><input type="hidden" name="_method" value="patch" />`
.

#form_tag_with_method_put
1. `ActionView::Helpers::FormTagHelper#utf8_enforcer_tag([])`
`<input name="utf8" type="hidden" value="&#x2713;" />`
1. `ActionView::Helpers::FormTagHelper#form_tag([{}, {:method=>:put}])`
`<form action="http://www.example.com" accept-charset="UTF-8" method="post"><input name="utf8" type="hidden" value="&#x2713;" /><input type="hidden" name="_method" value="put" />`
.

#form_tag
1. `ActionView::Helpers::FormTagHelper#utf8_enforcer_tag([])`
`<input name="utf8" type="hidden" value="&#x2713;" />`
1. `ActionView::Helpers::FormTagHelper#form_tag([])`
`<form action="http://www.example.com" accept-charset="UTF-8" method="post"><input name="utf8" type="hidden" value="&#x2713;" />`
.

#text_area_tag_id_sanitized
1. `ActionView::Helpers::FormTagHelper#text_area_tag(["item[][description]"])`
`<textarea name="item[][description]" id="item__description">
</textarea>`
.

#check_box_tag_default_checked
1. `ActionView::Helpers::FormTagHelper#check_box_tag(["admin", "1", true])`
`<input type="checkbox" name="admin" id="admin" value="1" checked="checked" />`
.

#label_tag_id_sanitized
1. `ActionView::Helpers::FormTagHelper#label_tag(["item[title]"])`
`<label for="item_title">Item[title]</label>`
.

#submit_tag_with_confirmation
1. `ActionView::Helpers::FormTagHelper#submit_tag(["Save", {:data=>{:confirm=>"Are you sure?"}}])`
`<input type="submit" name="commit" value="Save" data-confirm="Are you sure?" data-disable-with="Save" />`
.

#button_tag_with_submit_type
1. `ActionView::Helpers::FormTagHelper#button_tag(["Save", {:type=>"submit"}])`
`<button name="button" type="submit">Save</button>`
.

#select_tag_with_multiple
1. `ActionView::Helpers::FormTagHelper#select_tag(["colors", "<option>Red</option><option>Blue</option><option>Green</option>", {:multiple=>true}])`
`<select name="colors[]" id="colors" multiple="multiple"><option>Red</option><option>Blue</option><option>Green</option></select>`
.

#submit_tag_options_symbolize_keys_side_effects
1. `ActionView::Helpers::FormTagHelper#submit_tag(["submit value", {:option=>"random_option"}])`
`<input type="submit" name="commit" value="submit value" option="random_option" data-disable-with="submit value" />`
.

#label_tag_with_block_and_argument_and_options
1. `ActionView::Helpers::FormTagHelper#label_tag(["clock", {:id=>"label_clock"}])`
`<label id="label_clock" for="clock">Grandfather</label>`
.

#number_field_tag
1. `ActionView::Helpers::FormTagHelper#text_field_tag(["quantity", nil, {"type"=>"number", "min"=>1, "max"=>9}])`
`<input type="number" name="quantity" id="quantity" min="1" max="9" />`
1. `ActionView::Helpers::FormTagHelper#number_field_tag(["quantity", nil, {:in=>1...10}])`
`<input type="number" name="quantity" id="quantity" min="1" max="9" />`
.

#form_tag_with_remote
1. `ActionView::Helpers::FormTagHelper#embed_authenticity_token_in_remote_forms([])`
`false`
1. `ActionView::Helpers::FormTagHelper#utf8_enforcer_tag([])`
`<input name="utf8" type="hidden" value="&#x2713;" />`
1. `ActionView::Helpers::FormTagHelper#form_tag([{}, {:remote=>true}])`
`<form action="http://www.example.com" accept-charset="UTF-8" data-remote="true" method="post"><input name="utf8" type="hidden" value="&#x2713;" />`
.

#image_submit_tag_with_confirmation
1. `ActionView::Helpers::FormTagHelper#image_submit_tag(["save.gif", {:data=>{:confirm=>"Are you sure?"}}])`
`<input alt="Save" type="image" src="/images/save.gif" data-confirm="Are you sure?" />`
.

#email_field_tag
1. `ActionView::Helpers::FormTagHelper#text_field_tag(["address", nil, {:type=>:email}])`
`<input type="email" name="address" id="address" />`
1. `ActionView::Helpers::FormTagHelper#email_field_tag(["address"])`
`<input type="email" name="address" id="address" />`
.

#text_field_tag_size_string
1. `ActionView::Helpers::FormTagHelper#text_field_tag(["title", "Hello!", {"size"=>"75"}])`
`<input type="text" name="title" id="title" value="Hello!" size="75" />`
.

#submit_tag_with_no_onclick_options
1. `ActionView::Helpers::FormTagHelper#submit_tag(["Save", {:data=>{:disable_with=>"Saving..."}}])`
`<input type="submit" name="commit" value="Save" data-disable-with="Saving..." data-disable-with="Saving..." />`
.

#button_tag_with_block
1. `ActionView::Helpers::FormTagHelper#button_tag([])`
`<button name="button" type="submit">Content</button>`
.

#label_tag_with_block_and_argument
1. `ActionView::Helpers::FormTagHelper#label_tag(["clock"])`
`<label for="clock">Grandfather</label>`
.

#form_tag_enforce_utf8_false
1. `ActionView::Helpers::FormTagHelper#form_tag([{}, {:enforce_utf8=>false}])`
`<form action="http://www.example.com" accept-charset="UTF-8" method="post">`
.

#field_set_tag_in_erb
1. `ActionView::Helpers::FormTagHelper#field_set_tag(["Your details"])`
`<fieldset><legend>Your details</legend>Hello world!</fieldset>`
1. `ActionView::Helpers::FormTagHelper#field_set_tag([])`
`<fieldset>Hello world!</fieldset>`
1. `ActionView::Helpers::FormTagHelper#field_set_tag([""])`
`<fieldset>Hello world!</fieldset>`
1. `ActionView::Helpers::FormTagHelper#field_set_tag(["", {:class=>"format"}])`
`<fieldset class="format">Hello world!</fieldset>`
1. `ActionView::Helpers::FormTagHelper#field_set_tag([])`
`<fieldset></fieldset>`
1. `ActionView::Helpers::FormTagHelper#field_set_tag(["You legend!"])`
`<fieldset><legend>You legend!</legend></fieldset>`
.

#button_tag_with_button_type
1. `ActionView::Helpers::FormTagHelper#button_tag(["Button", {:type=>"button"}])`
`<button name="button" type="button">Button</button>`
.

#datetime_field_tag
1. `ActionView::Helpers::FormTagHelper#text_field_tag(["appointment", nil, {:type=>"datetime-local"}])`
`<input type="datetime-local" name="appointment" id="appointment" />`
1. `ActionView::Helpers::FormTagHelper#datetime_field_tag(["appointment"])`
`<input type="datetime-local" name="appointment" id="appointment" />`
.

#date_field_tag
1. `ActionView::Helpers::FormTagHelper#text_field_tag(["cell", nil, {:type=>:date}])`
`<input type="date" name="cell" id="cell" />`
1. `ActionView::Helpers::FormTagHelper#date_field_tag(["cell"])`
`<input type="date" name="cell" id="cell" />`
.

#submit_tag_having_data_disable_with_string
1. `ActionView::Helpers::FormTagHelper#submit_tag(["Save", {"data-disable-with"=>"Processing...", "data-confirm"=>"Are you sure?"}])`
`<input type="submit" name="commit" value="Save" data-confirm="Are you sure?" data-disable-with="Processing..." />`
.

#check_box_tag_disabled
1. `ActionView::Helpers::FormTagHelper#check_box_tag(["admin", "1", false, {:disabled=>true}])`
`<input type="checkbox" name="admin" id="admin" value="1" disabled="disabled" />`
.

#button_tag_with_reset_type
1. `ActionView::Helpers::FormTagHelper#button_tag(["Reset", {:type=>"reset"}])`
`<button name="button" type="reset">Reset</button>`
.

#telephone_field_tag
1. `ActionView::Helpers::FormTagHelper#text_field_tag(["cell", nil, {:type=>:tel}])`
`<input type="tel" name="cell" id="cell" />`
1. `ActionView::Helpers::FormTagHelper#telephone_field_tag(["cell"])`
`<input type="tel" name="cell" id="cell" />`
.

#radio_button_tag
1. `ActionView::Helpers::FormTagHelper#radio_button_tag(["people", "david"])`
`<input type="radio" name="people" id="people_david" value="david" />`
1. `ActionView::Helpers::FormTagHelper#radio_button_tag(["num_people", 5])`
`<input type="radio" name="num_people" id="num_people_5" value="5" />`
1. `ActionView::Helpers::FormTagHelper#radio_button_tag(["gender", "m"])`
`<input type="radio" name="gender" id="gender_m" value="m" />`
1. `ActionView::Helpers::FormTagHelper#radio_button_tag(["gender", "f"])`
`<input type="radio" name="gender" id="gender_f" value="f" />`
1. `ActionView::Helpers::FormTagHelper#radio_button_tag(["opinion", "-1"])`
`<input type="radio" name="opinion" id="opinion_-1" value="-1" />`
1. `ActionView::Helpers::FormTagHelper#radio_button_tag(["opinion", "1"])`
`<input type="radio" name="opinion" id="opinion_1" value="1" />`
1. `ActionView::Helpers::FormTagHelper#radio_button_tag(["person[gender]", "m"])`
`<input type="radio" name="person[gender]" id="person_gender_m" value="m" />`
1. `ActionView::Helpers::FormTagHelper#radio_button_tag(["ctrlname", "apache2.2"])`
`<input type="radio" name="ctrlname" id="ctrlname_apache2.2" value="apache2.2" />`
.

#select_tag_disabled
1. `ActionView::Helpers::FormTagHelper#select_tag(["places", "<option>Home</option><option>Work</option><option>Pub</option>", {:disabled=>true}])`
`<select name="places" id="places" disabled="disabled"><option>Home</option><option>Work</option><option>Pub</option></select>`
.

#form_tag_multipart
1. `ActionView::Helpers::FormTagHelper#utf8_enforcer_tag([])`
`<input name="utf8" type="hidden" value="&#x2713;" />`
1. `ActionView::Helpers::FormTagHelper#form_tag([{}, {"multipart"=>true}])`
`<form enctype="multipart/form-data" action="http://www.example.com" accept-charset="UTF-8" method="post"><input name="utf8" type="hidden" value="&#x2713;" />`
.

#select_tag_with_nil_option_tags_and_include_blank
1. `ActionView::Helpers::FormTagHelper#select_tag(["places", nil, {}])`
`<select name="places" id="places"><option value="" label=" "></option></select>`
.

#password_field_tag
1. `ActionView::Helpers::FormTagHelper#text_field_tag(["password", nil, {:type=>:password}])`
`<input type="password" name="password" id="password" />`
1. `ActionView::Helpers::FormTagHelper#password_field_tag([])`
`<input type="password" name="password" id="password" />`
.

#url_field_tag
1. `ActionView::Helpers::FormTagHelper#text_field_tag(["homepage", nil, {:type=>:url}])`
`<input type="url" name="homepage" id="homepage" />`
1. `ActionView::Helpers::FormTagHelper#url_field_tag(["homepage"])`
`<input type="url" name="homepage" id="homepage" />`
.

#file_field_tag_with_options
1. `ActionView::Helpers::FormTagHelper#text_field_tag(["picsplz", nil, {:class=>"pix", :type=>:file}])`
`<input type="file" name="picsplz" id="picsplz" class="pix" />`
1. `ActionView::Helpers::FormTagHelper#file_field_tag(["picsplz", {:class=>"pix"}])`
`<input type="file" name="picsplz" id="picsplz" class="pix" />`
.

#hidden_field_tag
1. `ActionView::Helpers::FormTagHelper#text_field_tag(["id", 3, {:type=>:hidden}])`
`<input type="hidden" name="id" id="id" value="3" />`
1. `ActionView::Helpers::FormTagHelper#hidden_field_tag(["id", 3])`
`<input type="hidden" name="id" id="id" value="3" />`
.

#text_area_tag_should_disregard_size_if_its_given_as_an_integer
1. `ActionView::Helpers::FormTagHelper#text_area_tag(["body", "hello world", {:size=>20}])`
`<textarea name="body" id="body">
hello world</textarea>`
.

#select_tag_with_nil_option_tags_and_prompt
1. `ActionView::Helpers::FormTagHelper#select_tag(["places", nil, {}])`
`<select name="places" id="places"><option value="">string</option></select>`
.

#submit_tag_with_symbol_value
1. `ActionView::Helpers::FormTagHelper#submit_tag([:Save])`
`<input type="submit" name="commit" value="Save" data-disable-with="Save" />`
.

#submit_tag_doesnt_have_data_disable_with_twice
1. `ActionView::Helpers::FormTagHelper#submit_tag(["Save", {"data-disable-with"=>"Processing...", "data-confirm"=>"Are you sure?"}])`
`<input type="submit" name="commit" value="Save" data-confirm="Are you sure?" data-disable-with="Processing..." />`
.

#select_tag_with_include_blank_false
1. `ActionView::Helpers::FormTagHelper#select_tag(["places", "<option>Home</option><option>Work</option><option>Pub</option>", {}])`
`<select name="places" id="places"><option>Home</option><option>Work</option><option>Pub</option></select>`
.

#text_field_tag_maxlength_symbol
1. `ActionView::Helpers::FormTagHelper#text_field_tag(["title", "Hello!", {:maxlength=>75}])`
`<input type="text" name="title" id="title" value="Hello!" maxlength="75" />`
.

#select_tag_with_include_blank_string
1. `ActionView::Helpers::FormTagHelper#select_tag(["places", "<option>Home</option><option>Work</option><option>Pub</option>", {}])`
`<select name="places" id="places"><option value="">Choose</option><option>Home</option><option>Work</option><option>Pub</option></select>`
.

#label_tag_without_text
1. `ActionView::Helpers::FormTagHelper#label_tag(["title"])`
`<label for="title">Title</label>`
.

#text_area_tag_options_symbolize_keys_side_effects
1. `ActionView::Helpers::FormTagHelper#text_area_tag(["body", "hello world", {:option=>"random_option"}])`
`<textarea name="body" id="body" option="random_option">
hello world</textarea>`
.

#text_area_tag_unescaped_content
1. `ActionView::Helpers::FormTagHelper#text_area_tag(["body", "<b>hello world</b>", {:size=>"20x40", :escape=>false}])`
`<textarea name="body" id="body" cols="20" rows="40">
<b>hello world</b></textarea>`
.

#text_area_tag_size_symbol
1. `ActionView::Helpers::FormTagHelper#text_area_tag(["body", "hello world", {:size=>"20x40"}])`
`<textarea name="body" id="body" cols="20" rows="40">
hello world</textarea>`
.

#text_area_tag_unescaped_nil_content
1. `ActionView::Helpers::FormTagHelper#text_area_tag(["body", nil, {:escape=>false}])`
`<textarea name="body" id="body">
</textarea>`
.

#check_box_tag_id_sanitized
1. `ActionView::Helpers::FormTagHelper#check_box_tag(["project[2][admin]"])`
`<input type="checkbox" name="project[2][admin]" id="project_2_admin" value="1" />`
.

#select_tag_escapes_prompt
1. `ActionView::Helpers::FormTagHelper#select_tag(["places", "<option>Home</option><option>Work</option><option>Pub</option>", {}])`
`<select name="places" id="places"><option value="">&lt;script&gt;alert(1337)&lt;/script&gt;</option><option>Home</option><option>Work</option><option>Pub</option></select>`
.

#button_tag_with_block_and_options
1. `ActionView::Helpers::FormTagHelper#button_tag([{:name=>"temptation", :type=>"button"}])`
`<button name="temptation" type="button"><strong>Do not press me</strong></button>`
.

#multiple_field_tags_with_same_options
1. `ActionView::Helpers::FormTagHelper#text_field_tag(["title", nil, {:class=>"important", :type=>:file}])`
`<input type="file" name="title" id="title" class="important" />`
1. `ActionView::Helpers::FormTagHelper#file_field_tag(["title", {:class=>"important"}])`
`<input type="file" name="title" id="title" class="important" />`
1. `ActionView::Helpers::FormTagHelper#text_field_tag(["title", "Hello!", {:class=>"important", :type=>:password}])`
`<input type="password" name="title" id="title" value="Hello!" class="important" />`
1. `ActionView::Helpers::FormTagHelper#password_field_tag(["title", "Hello!", {:class=>"important"}])`
`<input type="password" name="title" id="title" value="Hello!" class="important" />`
1. `ActionView::Helpers::FormTagHelper#text_field_tag(["title", "Hello!", {:class=>"important"}])`
`<input type="text" name="title" id="title" value="Hello!" class="important" />`
.

#text_area_tag_size_string
1. `ActionView::Helpers::FormTagHelper#text_area_tag(["body", "hello world", {"size"=>"20x40"}])`
`<textarea name="body" id="body" cols="20" rows="40">
hello world</textarea>`
.

#submit_tag_having_data_hash_disable_with_boolean
1. `ActionView::Helpers::FormTagHelper#submit_tag(["Save", {:data=>{:confirm=>"Are you sure?"}}])`
`<input type="submit" name="commit" value="Save" data-confirm="Are you sure?" />`
.

#select_tag_with_prompt_and_include_blank
1. `ActionView::Helpers::FormTagHelper#select_tag(["places", "<option>Home</option><option>Work</option><option>Pub</option>", {}])`
`<select name="places" id="places"><option value="">string</option><option value="" label=" "></option><option>Home</option><option>Work</option><option>Pub</option></select>`
.

#color_field_tag
1. `ActionView::Helpers::FormTagHelper#text_field_tag(["car", nil, {:type=>:color}])`
`<input type="color" name="car" id="car" />`
1. `ActionView::Helpers::FormTagHelper#color_field_tag(["car"])`
`<input type="color" name="car" id="car" />`
.

#image_label_tag_options_symbolize_keys_side_effects
1. `ActionView::Helpers::FormTagHelper#label_tag(["submit source", "title", {:option=>"random_option"}])`
`<label option="random_option" for="submit_source">title</label>`
.

#search_field_tag
1. `ActionView::Helpers::FormTagHelper#text_field_tag(["query", nil, {:type=>:search}])`
`<input type="search" name="query" id="query" />`
1. `ActionView::Helpers::FormTagHelper#search_field_tag(["query"])`
`<input type="search" name="query" id="query" />`
.

#empty_submit_tag
1. `ActionView::Helpers::FormTagHelper#submit_tag(["Save"])`
`<input type="submit" name="commit" value="Save" data-disable-with="Save" />`
.

#select_tag_with_include_blank
1. `ActionView::Helpers::FormTagHelper#select_tag(["places", "<option>Home</option><option>Work</option><option>Pub</option>", {}])`
`<select name="places" id="places"><option value="" label=" "></option><option>Home</option><option>Work</option><option>Pub</option></select>`
.

#text_field_tag_class_string
1. `ActionView::Helpers::FormTagHelper#text_field_tag(["title", "Hello!", {"class"=>"admin"}])`
`<input type="text" name="title" id="title" value="Hello!" class="admin" />`
.

#text_field_tag_id_sanitized
1. `ActionView::Helpers::FormTagHelper#text_field_tag(["item[][title]"])`
`<input type="text" name="item[][title]" id="item__title" />`
.

#select_tag_with_prompt
1. `ActionView::Helpers::FormTagHelper#select_tag(["places", "<option>Home</option><option>Work</option><option>Pub</option>", {}])`
`<select name="places" id="places"><option value="">string</option><option>Home</option><option>Work</option><option>Pub</option></select>`
.

#text_field_tag_maxlength_string
1. `ActionView::Helpers::FormTagHelper#text_field_tag(["title", "Hello!", {"maxlength"=>"75"}])`
`<input type="text" name="title" id="title" value="Hello!" maxlength="75" />`
.

#button_tag_defaults_with_block_and_options
1. `ActionView::Helpers::FormTagHelper#button_tag([{:name=>"temptation", :value=>"within"}])`
`<button name="temptation" type="submit" value="within"><strong>Do not press me</strong></button>`
.

#month_field_tag
1. `ActionView::Helpers::FormTagHelper#text_field_tag(["birthday", nil, {:type=>:month}])`
`<input type="month" name="birthday" id="birthday" />`
1. `ActionView::Helpers::FormTagHelper#month_field_tag(["birthday"])`
`<input type="month" name="birthday" id="birthday" />`
.

#text_field_tag_size_symbol
1. `ActionView::Helpers::FormTagHelper#text_field_tag(["title", "Hello!", {:size=>75}])`
`<input type="text" name="title" id="title" value="Hello!" size="75" />`
.

#button_tag_options_symbolize_keys_side_effects
1. `ActionView::Helpers::FormTagHelper#button_tag(["button value", {:option=>"random_option"}])`
`<button name="button" type="submit" option="random_option">button value</button>`
.

#stringify_symbol_keys
1. `ActionView::Helpers::FormTagHelper#text_field_tag(["title", "Hello!", {:id=>"admin"}])`
`<input type="text" name="title" id="admin" value="Hello!" />`
.

#form_tag_with_block_in_erb
1. `ActionView::Helpers::FormTagHelper#utf8_enforcer_tag([])`
`<input name="utf8" type="hidden" value="&#x2713;" />`
1. `ActionView::Helpers::FormTagHelper#form_tag(["http://www.example.com"])`
`<form action="http://www.example.com" accept-charset="UTF-8" method="post"><input name="utf8" type="hidden" value="&#x2713;" />Hello world!</form>`
.

#button_tag_with_disabled_option
1. `ActionView::Helpers::FormTagHelper#button_tag(["Reset", {:type=>"reset", :disabled=>true}])`
`<button name="button" type="reset" disabled="disabled">Reset</button>`
.

#text_field_tag
1. `ActionView::Helpers::FormTagHelper#text_field_tag(["title", "Hello!"])`
`<input type="text" name="title" id="title" value="Hello!" />`
.

#week_field_tag
1. `ActionView::Helpers::FormTagHelper#text_field_tag(["birthday", nil, {:type=>:week}])`
`<input type="week" name="birthday" id="birthday" />`
1. `ActionView::Helpers::FormTagHelper#week_field_tag(["birthday"])`
`<input type="week" name="birthday" id="birthday" />`
.

#button_tag
1. `ActionView::Helpers::FormTagHelper#button_tag([])`
`<button name="button" type="submit">Button</button>`
.

#submit_tag
1. `ActionView::Helpers::FormTagHelper#submit_tag(["Save", {:onclick=>"alert('hello!')", :data=>{:disable_with=>"Saving..."}}])`
`<input type="submit" name="commit" value="Save" onclick="alert(&#39;hello!&#39;)" data-disable-with="Saving..." data-disable-with="Saving..." />`
.

#range_input_tag
1. `ActionView::Helpers::FormTagHelper#text_field_tag(["volume", nil, {"step"=>0.1, "type"=>:range, "min"=>0, "max"=>11}])`
`<input type="range" name="volume" id="volume" step="0.1" min="0" max="11" />`
1. `ActionView::Helpers::FormTagHelper#number_field_tag(["volume", nil, {:in=>0..11, :step=>0.1, :type=>:range}])`
`<input type="range" name="volume" id="volume" step="0.1" min="0" max="11" />`
1. `ActionView::Helpers::FormTagHelper#range_field_tag(["volume", nil, {:in=>0..11, :step=>0.1}])`
`<input type="range" name="volume" id="volume" step="0.1" min="0" max="11" />`
.

#hidden_field_tag_id_sanitized
1. `ActionView::Helpers::FormTagHelper#text_field_tag(["item[][title]", nil, {:type=>:hidden}])`
`<input type="hidden" name="item[][title]" id="item__title" />`
1. `ActionView::Helpers::FormTagHelper#hidden_field_tag(["item[][title]"])`
`<input type="hidden" name="item[][title]" id="item__title" />`
.

#button_tag_escape_content
1. `ActionView::Helpers::FormTagHelper#button_tag(["<b>Reset</b>", {:type=>"reset", :disabled=>true}])`
`<button name="button" type="reset" disabled="disabled">&lt;b&gt;Reset&lt;/b&gt;</button>`
.

Finished in 0.094083s, 1084.1491 runs/s, 1349.8719 assertions/s.

102 runs, 127 assertions, 0 failures, 0 errors, 0 skips
