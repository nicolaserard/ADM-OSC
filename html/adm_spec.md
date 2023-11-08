
# ADM-OSC v0.4

## polar position messages

<style>
  .tr { background-color: lightblue; }
</style>

<table>
    <thead bgcolor="Green">
        <tr>
            <th colspan=2 style="color:#FFFFFF">osc address</th>
            <th style="color:#FFFFFF">type</th>
            <th style="color:#FFFFFF">units</th>               
            <th style="color:#FFFFFF">min</th>
            <th style="color:#FFFFFF">max</th>
            <th style="color:#FFFFFF">default</th>
            <th style="color:#FFFFFF">description</th>
            <th style="color:#FFFFFF">example</th>
            <th style="color:#FFFFFF">status</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td rowspan=6>/adm/obj/<span style="font-style:italic">n</span></td>
            <td>/azim</td>
            <td>float</td>
            <td>degrees</td>
            <td>-180.0</td>
            <td>180.0</td>
            <td>-</td>
            <td><b>azimuth</b> “theta - &#952;” of sound location. -90 is on the Right, 0 is in front.</td>
            <td>/adm/obj/4/azim -22.5</td>
            <td bgcolor="LightGreen">stable v0.4</td>
        </tr>
        <tr>
            <td>/elev</td>
            <td>float</td>
            <td>degrees</td>
            <td>-90.0</td>
            <td>90.0</td>
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
            <td>/widthDeg</td>
            <td>float</td>
            <td>degrees</td>
            <td>0.0</td>
            <td>180.0</td>
            <td>0.0</td>
            <td>horizontal extent in degrees. See also /w</td>
            <td>/adm/obj/3/widthDeg 45.2</td>
            <td bgcolor="Pink"><a href="https://github.com/immersive-audio-live/ADM-OSC/issues/1">in progress</a></td>
        </tr>
        <tr>
            <td>/gain</td>
            <td>float</td>
            <td>linear</td>
            <td>0.</td>
            <td></td>
            <td>1.0</td>
            <td>Apply a gain to the audio in the object.</td>
            <td>/adm/obj/3/gain 0.707</td>
            <td bgcolor="LightGreen">stable v0.4</td>
        </tr>
    </tbody>
</table>

## Cartiesian position messages