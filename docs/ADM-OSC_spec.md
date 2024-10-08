# ADM-OSC Draft v0.5
All messages can be part of a preset. The preset can be enumerated by adding `/preset/n` before any of the messages below.

## Dynamic messages
Dynamic messages, such as object postions, have the potential to change rapidly over the course of a program. They exist in a separate namespace so they can be prioritized for maximum temporal accuracy.

### Dynamic messages for objects &mdash; polar coordinates

<table>
    <thead>
        <tr>
            <th colspan=3>osc address</th>
            <th>type</th>
            <th>units</th>
            <th>min</th>
            <th>max</th>
            <th width="100px">default</th>
            <th width="500px">description</th>
            <th width="300px">example</th>
            <th>status</th>
        </tr>
    </thead>
    <tbody>
        <tr>
        <td rowspan=8>/adm</td>
            <td rowspan=6>/obj/<i>(object number)</i></td>
            <td>/azim</td>
            <td>float</td>
            <td>degrees</td>
            <td>-180.</td>
            <td>180.</td>
            <td>-</td>
            <td><b>azimuth</b> “theta - &#952;” of sound location. -90 is on the Right, 0 is in front.</td>
            <td>/adm/obj/4/azim -22.5</td>
            <td bgcolor="LightGreen">stable v0.4</td>
        </tr>
        <tr>
            <td>/elev</td>
            <td>float</td>
            <td>degrees</td>
            <td>-90.</td>
            <td>90.</td>
            <td>-</td>
            <td><b>elevation</b> “phi - &#632;” of sound location</td>
            <td>/adm/obj/4/elev 12.7</td>
            <td bgcolor="LightGreen">stable v0.4</td>
        </tr>
        <tr>
            <td>/dist</td>
            <td>float</td>
            <td>normalized</td>
            <td>0.0</td>
            <td>1.0</td>
            <td>1.0</td>
            <td><b>distance</b> “r” from origin</td>
            <td>/adm/obj/4/dist 0.9</td>
            <td bgcolor="LightGreen">stable v0.4</td>
        </tr>
        <tr>
            <td>/aed</td>
            <td>list</td>
            <td colspan=4>see above</td>
            <td>compact format enables synchronicity of position changes and also less network traffic</td>
            <td>/adm/obj/4/aed -22.5 12.7 0.9</td>
            <td bgcolor="LightGreen">stable v0.4</td>
        </tr>
        <tr>
            <td>/w</td>
            <td>float</td>
            <td>linear</td>
            <td>0.</td>
            <td></td>
            <td>0.0</td>
            <td>X-width</td>
            <td>/adm/obj/3/w 45.2</td>
            <td bgcolor="Pink"><a href="https://github.com/immersive-audio-live/ADM-OSC/issues/1">in progress</a></td>
        </tr>
        <tr>
            <td>/gain</td>
            <td>float</td>
            <td>normalized</td>
            <td>0.</td>
            <td></td>
            <td>1.0</td>
            <td>Apply a gain to the audio in the object.</td>
            <td>/adm/obj/3/gain 0.707</td>
            <td bgcolor="LightGreen">stable v0.4</td>
        </tr>
         <tr>
            <td rowspan=2>/prog/<i>(program number)</i>/obj/<i>(object number)</i></td>
            <td>/azim</td>
            <td>float</td>
            <td>degrees</td>
            <td>-180.</td>
            <td>180.</td>
            <td>-</td>
            <td><b>azimuth</b> “theta - &#952;” of sound location. -90 is on the Right, 0 is in front.</td>
            <td>/adm/prog/2/obj/4/azim -22.5</td>
            <td bgcolor="LightYellow"><b>proposed v0.5</b></td>
        </tr>
         <tr>
            <td>/elev</td>
            <td>float</td>
            <td>degrees</td>
            <td>-90.</td>
            <td>90.</td>
            <td>-</td>
            <td><b>elevation</b> “phi - &#632;” of sound location</td>
            <td>/adm/prog/2/obj/4/elev 12.7</td>
            <td bgcolor="LightYellow"><b>proposed v0.5</b></td>
        </tr>
        <tr>
            <td>/dist</td>
            <td>float</td>
            <td>normalized</td>
            <td>0.0</td>
            <td>1.0</td>
            <td>1.0</td>
            <td><b>distance</b> “r” from origin</td>
            <td>/adm/prog/2/obj/4/dist 0.9</td>
            <td bgcolor="LightYellow"><b>proposed v0.5</b></td>
        </tr>
    </tbody>
</table>

### Dynamic messages for objects &mdash; cartesian coordinates

<table>
    <thead>
        <tr>
            <th colspan=3>osc address</th>
            <th>type</th>
            <th>units</th>
            <th>min</th>
            <th>max</th>
            <th>default</th>
            <th width="500px">description</th>
            <th width="300px">example</th>
            <th>status</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td rowspan=8>/adm</td>
            <td rowspan=6>/obj/<i>(object number)</i></td>
            <td>/x</td>
            <td>float</td>
            <td>normalized</td>
            <td>-1.0</td>
            <td>1.0</td>
            <td>0.0</td>
            <td>left/right dimension. -1 is left</td>
            <td>/adm/obj/4/x -0.9</td>
            <td bgcolor="LightGreen">stable v0.4</td>
        </tr>
        <tr>
            <td>/y</td>
            <td>float</td>
            <td>normalized</td>
            <td>-1.0</td>
            <td>1.0</td>
            <td>0.0</td>
            <td>front/back dimension</td>
            <td>/adm/obj/4/y 0.15</td>
            <td bgcolor="LightGreen">stable v0.4</td>
        </tr>
        <tr>
            <td>/z</td>
            <td>float</td>
            <td>normalized</td>
            <td>-1.0</td>
            <td>1.0</td>
            <td>0.0</td>
            <td>top/bottom dimension</td>
            <td>/adm/obj/4/z 0.7</td>
            <td bgcolor="LightGreen">stable v0.4</td>
        </tr>
         <tr>
            <td>/xyz</td>
            <td>list</td>
            <td colspan=4>see above</td>
            <td>compact format enables synchronicity of position changes and also less network traffic</td>
            <td>/adm/obj/4/xyz -0.9 0.15 0.7</td>
            <td bgcolor="LightGreen">stable v0.4</td>
        </tr>
            <td>/w</td>
            <td>float</td>
            <td>normalized</td>
            <td>0.0</td>
            <td>1.0</td>
            <td>0.0</td>
            <td>When mapped to ADM, companion sub-elements depth and height are also included but set to 0.0</td>
            <td>/adm/obj/3/w 45.2</td>
            <td bgcolor="LightYellow"><b>proposed v0.5</b></td>
        </tr>
        <tr>
            <td>/gain</td>
            <td>float</td>
            <td>normalized</td>
            <td></td>
            <td></td>
            <td>Apply a gain to the audio in the object.</td>
            <td>/adm/obj/3/gain 0.707</td>
            <td bgcolor="LightGreen">stable v0.4</td>
        </tr>
        <tr>
            <td rowspan=2>/prog/<i>(program number)</i>/obj/<i>(object number)</i></td>
            <td>/x</td>
            <td>float</td>
            <td>normalized</td>
            <td>-1.</td>
            <td>1.</td>
            <td>left/right dimension. -1 is left</td>
            <td>/adm/obj/4/x -0.9</td>
            <td bgcolor="LightYellow"><b>proposed v0.5</b></td>
        </tr>
         <tr>
            <td>/y</td>
            <td>float</td>
            <td>normalized</td>
            <td>-1.</td>
            <td>1.</td>
            <td>front/back dimension</td>
            <td>/adm/obj/4/y 0.15</td>
            <td bgcolor="LightYellow"><b>proposed v0.5</b></td>
        </tr>
    </tbody>
</table>

## Static messages

Data which doesn't change very often is included in a `/config` namespace. This lets a receiver know that timing is not critical and the message can be handled at a lower priority.

### static object messages

<table>
    <thead>
        <tr>
            <th colspan=4>osc address</th>
            <th>type</th>
            <th>units</th>
            <th>min</th>
            <th>max</th>
            <th width="500px">description</th>
            <th width="300px">example</th>
            <th>status</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td rowspan=8>/adm</td>
            <td rowspan=6>/config</td>
            <td rowspan=3>/obj/<i>(object number)</i></td>
            <td>/cartesian</td>
            <td>int</td>
            <td>true/false</td>
            <td>0</td>
            <td>1</td>
            <td>If the flag is set to 1, Cartesian coordinates are used. Otherwise spherical coordinates are used.</td>
            <td>/adm/config/obj/1/cartesian 0</td>
            <td bgcolor="LightGreen">stable v0.4</td>
        </tr>
        <tr>
            <td>/absdistance</td>
            <td>float</td>
            <td>meters</td>
            <td></td>
            <td></td>
            <td>Distance signified by a normalized value of 1</td>
            <td>/adm/config/obj/1/absdistance 21.3</td>
            <td bgcolor="LightYellow"><b>proposed v0.5</b></td>
        </tr>
         <tr>
            <td>/refdistance</td>
            <td>float</td>
            <td>normalized</td>
            <td>0.</td>
            <td>1</td>
            <td>Distance where dimensionless rendering is replaced with with physics-based rendering. (default = 1.0)</td>
            <td>/adm/config/obj/1/refdistance 0.2</td>
            <td bgcolor="LightYellow"><b>proposed v0.5</b></td>
        </tr>
        <tr>
            <td rowspan=3>/bed/<i>(bed number)</i></td>
            <td>/chan</td>
            <td>int</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td bgcolor="LightYellow"><b>proposed v0.5</b></td>
        </tr>
         <tr>
            <td>/name</td>
            <td>symbol</td>
             <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td bgcolor="LightYellow"><b>proposed v0.5</b></td>
        </tr>
         <tr>
            <td>/format</td>
            <td>int</td>
            <td colspan=4>see table below</td>
            <td></td>
            <td bgcolor="LightYellow"><b>proposed v0.5</b></td>
        </tr>
     </tbody>
</table>  

#### Bed format values
<table>
    <thead>
        <tr>
            <th>bed format</th>
            <th>value</th>
        </tr>
    </thead>
    <tbody>
    <tr>
        <td>2.0</td>
        <td>2</td>
    <tr>
    <tr>
        <td>3.0</td>
        <td>10</td>
    <tr>
    <tr>
        <td>5.0</td>
        <td>12</td>
    <tr>
    <tr>
        <td>5.1</td>
        <td>3</td>
    <tr>
    <tr>
        <td>5.1.2</td>
        <td>19</td>
    <tr>
    <tr>
        <td>5.1.4</td>
        <td>5</td>
    <tr>
    <tr>
        <td>7.1.4</td>
        <td>23</td>
    <tr>
    </tbody>
</table>

### Static programme messages

<table>
    <thead>
        <tr>
            <th colspan=5>osc address</th>
            <th>type</th>
            <th>units</th>
            <th>min</th>
            <th>max</th>
            <th width="500px">description</th>
            <th width="300px">example</th>
            <th>status</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td rowspan=13>/adm</td>
            <td rowspan=13>/prog/<i>(prog number)</i></td>
            <td rowspan=13>/config</i></td>
            <td rowspan=3>/template</td>
            <td>/name</td>
            <td>symbol</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td>/adm/prog/2/template/name "English AD"</td>
            <td bgcolor="LightYellow"><b>proposed v0.5</b></td>
        </tr>
        <tr>
            <td>/version</td>
            <td>symbol</td>
            <td>x.x.x</td>
            <td></td>
            <td></td>
            <td></td>
            <td>/adm/prog/2/template/version 3.2.1</td>
            <td bgcolor="LightYellow"><b>proposed v0.5</b></td>
        </tr>
            <td>/level</td>
            <td>int</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td>/adm/prog/2/template/format 23</td>
            <td bgcolor="LightYellow"><b>proposed v0.5</b></td>
        </tr>
        <tr>
            <td rowspan=2>/label/<i>(label num)</i></td>
            <td>/lang</td>
            <td>symbol</td>
            <td>ISO 639-1?</td>
            <td></td>
            <td></td>
            <td>Used for local language labeling</td>
            <td>/adm/prog/2/label/3/lang FR</td>
            <td bgcolor="LightYellow"><b>proposed v0.5</b></td>
        </tr>
        <tr>
         <td>/name</td>
            <td>symbol</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td>/adm/prog/2/label/3/name "name"</td>
            <td bgcolor="LightYellow"><b>proposed v0.5</b></td>
        </tr>
        <tr>
            <td rowspan=4>/bed/<i>(bed num)</i></td>
            <td>/chan</td>
            <td>int</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td>/adm/prog/2/bed/1/chan</td>
            <td bgcolor="LightYellow"><b>proposed v0.5</b></td>
        </tr>
        <tr>
            <td>/name</td>
            <td>symbol</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td>/adm/prog/2/bed/1/name "name"</td>
            <td bgcolor="LightYellow"><b>proposed v0.5</b></td>
        </tr>
        <td>/layout</td>
            <td>int</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td>/adm/prog/2/bed/1/layout</td>
            <td bgcolor="LightYellow"><b>proposed v0.5</b></td>
        </tr>
        <td>/gain</td>
            <td>float</td>
            <td>0.0</td>
            <td></td>
            <td></td>
            <td>1.0</td>
            <td>/adm/prog/2/bed/1/gain 0.7</td>
            <td bgcolor="LightYellow"><b>proposed v0.5</b></td>
        </tr>
        <tr>
            <td rowspan=4>/obj/<i>(object num)</i></td>
            <td>/cartesian</td>
            <td>int</td>
            <td>true/false</td>
            <td>0</td>
            <td>1</td>
            <td></td>
            <td>/adm/prog/2/obj/5/cartesian 1</td>
            <td bgcolor="LightYellow"><b>proposed v0.5</b></td>
        </tr>
        <tr>
            <td>/chan</td>
            <td>int</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td>/adm/prog/2/obj/6/chan 7</td>
            <td bgcolor="LightYellow"><b>proposed v0.5</b></td>
        </tr>
        <tr>
            <td>/name</td>
            <td>symbol</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td>/adm/prog/2/obj/7/name "name"</td>
            <td bgcolor="LightYellow"><b>proposed v0.5</b></td>
        </tr>
    </tbody>
</table> 
