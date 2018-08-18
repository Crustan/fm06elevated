## Conditionals
Here are the kind of conditionals in the game I've found during rebuilding this skin. 
mode="0" equals to ===
mode="1" equals to !==
no mode attribute equals mode="0"

#### Hide if fullscreen mode
    <attachment class="test_global_attachment" get_property="FS  " value="true" mode="0" set_property="hidn" skip_if_null="false" skip_if_resetting="false"/>

#### Hide if not fullscreen mode
    <attachment class="test_global_attachment" get_property="FS  " value="true" mode="1" set_property="hidn" skip_if_null="false" skip_if_resetting="false"/>

#### Hide if preferences screen
    <attachment class="test_global_attachment" get_property="scid" value="2" mode="1" set_property="hidn" skip_if_null="false" skip_if_resetting="false" priority="1"/>

#### Hide if the game isn't set up yet 
    <attachment class="test_global_attachment" get_property="scid" set_property="hidn" skip_if_false="false">
	  <unsigned id="value" value="1"/>
	</attachment>

#### Hide if history back is disabled
    <attachment class="test_global_attachment" get_property="disp" value="1" skip_if_null="false" set_property="hidn"/>

#### Hide if history forward is disabled
    <attachment class="test_global_attachment" get_property="disn" value="1" skip_if_null="false" set_property="hidn"/>

#### Hide if Match
    <attachment class="test_global_attachment" get_property="scid" value="22" set_property="hidn" skip_if_null="false" />

#### Hide if not match (mode = 1)
    <attachment class="test_global_attachment" get_property="scid" value="22" mode="1" set_property="hidn" skip_if_null="false" skip_if_resetting="false" priority="1"/>

#### Hide if no main logo
    <attachment class="test_global_attachment" get_property="mnpc" skip_if_null="false" set_property="hidn"/>

#### Hide if no second team logo
    <attachment class="test_global_attachment" get_property="scpc" skip_if_null="false" set_property="hidn"/>

#### Hide if no subtitle
    <attachment class="test_global_attachment" get_property="subt" skip_if_null="false" set_property="hidn"/>


## Layout attributes
Layouting FM elements is a tricky part of skinning. There are numerous of layout classes and some are more common than others. Here are the ones I've found and a little explanation of each.

    <layout class="stick_to_sides_attachment" alignment="all" inset="0"/>

    <layout class="fill_space_attachment"/>
Fills the element in parent. Good for elements that have responsive measure (eg. -1), and maybe has other elements on the side.

## Screen ID:s
Every screen ha an ID that's used for disabling, enabling different components (see Conditionals above)

* Intro/Start - 2
* Match - 22