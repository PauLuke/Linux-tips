I noticed how to do that!

I deleted what was before in the snippet file and put the following:

```
/*Center Image*/
img:is([alt*="ctr"], [alt*="center"]),
.image-embed[src*="#ctr"] .image-embed[alt*=ctr],
.image-embed[src*="#center"] .image-embed[alt*=center],
.imgctr img {
display: block;
margin-left: auto;
margin-right: auto;
}
```

And in the note I put:

```
![[image.png|center|200]]
```

[Relevant link](https://youtu.be/VRoBNWvw8sU)