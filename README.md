# 3DGS-Compression
The 3DGS is a scence representation, then what we can do in the compression 
# what in 3DGS
1.center/position 2.covariance 3.opacity 4.color 5.sphericao harmonics(SH)
that is 3×1 position vector 3×1 scale vector 4×1 rotation quaternion 
1 scalar opacity and SH coefficients(if degree-3 SH,it means ,we need 48 coefficients).and all of them are 32-bit float
# every parameter 
position determines the gaussian where is,scale+rotation determine its shape in space is an ellipsoid. 
If the gaussian with very low opacity often contribute little to the final pixel count, so they are frequently pruned.So
The more SH coefficients there are, the stronger the correlation between color and viewpoint, but the more expensive the storage becomes. 
Therefore, many methods reduce SH, even utilizing SH gradients or performing adaptive shaving during pruning.
# what we can do in 3DGS compression
# 1.reduce the number of gaussian
Which Gaussian types are redundant? 
Which Gaussian types contribute little to image quality? 
Which Gaussian types can be replaced by other Gaussian types?
# 2.quantization
1.Quantize each attribute individually.
2.Map a set of properties to the codebook
Can the position be lowered? 
Can the bit scale/rotation be lowered? 
Can the bit opacity be lowered? 
Can the bit SH be lowered?
# 3.structured compression
