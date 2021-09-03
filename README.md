# renderSBS
A fast tox to transform any 3D render in TouchDesigner in a 3D content for 3D projectors or TV (SideBySide or TopBottom)

renderSBS alpha version 0.1.01
by Simone "Simplo" Murtas
https://github.com/simplo

It works, but has to be tested in different environments.
Probably it has still many problems to be fixed.
So why I released it?
Just because I don't really know when I fill find the time to test it properly, so maybe that if I wait it will never be released.

renderSBS is a TOX made to help testing SBS 3D projections.

I needed some kind of 3D content from TouchDesigner to test a 3D projector setup with acrive glasses.
Instead of waste time building different 3D scenarios, I tought it could be great to have a component able to be copied in any 3D TouchDesigner scenario (SOPs & Geos + camera + lights + render) and transform it in an SBS 3D output.

How to use it:
Just put renderSBS in the container with your main render: you just have to assign your existing render to the "render" parameter of the tox and it will return an SBS rendering as output, according to the "intereye" parameter you choose.
You can choose between SBS (side by side) 3D image or top/bottom.

What it does:
Basically it takes the original point of view of the camera in your original render as LEFT EYE camera, then creates a RIGHT EYE camera at "intereye" distance from that and take both tangent to the point of view.
Theoretically you don't need to make anything, just set the "intereye" value as you like.
All rendering specs, camera movements etc will be replicated.

1) gets all the "render" parameter and duplicates them on the LEFT and RIGHT renders, so you'll get same results in term of lens, angle of view and flags.
2) use same lights as the original render
3) use same geos as the originale render
4) gets the original camera and set all the parameters to the two cameras (LEFT and RIGHT)
5) changes all the parameters in real time, so if your camera moves, for instance, also the two cameras will move in the same way.

Controls:
	- CTRL+3 / CTRL+4 decrease/increase the intereye value to set the best 3D effect. Steps are very small so you have to press them many times to see sibstantial diffrences.
	- CTRL+f shows the rendering in perform mode
	

Possible issues:
I'm sure renderSBS cannot work in every situation, the more your render is complicated the more are the probabilities of problems.
Probably I didn't considered any situation, especially in terms of elaborated camera movements (for example the path option etc).

Every feedback will be appreciated.

This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.
Please mention the author.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.


