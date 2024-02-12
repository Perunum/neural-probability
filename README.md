# Neural Probability

## Overview
This repository contains a set of general functions which handle the neural networks in our framework. There are no packages required.

## How to use
The functions can be used in a Julia application by copying the code and adding `include("pTUM-base-2.0.jl")`.

## Continuous distributions

### Function initDist
```julia
w,b,npars = initDist(nvars,layers1,layers2;shift=0.1)
```
### Function fitDist
```julia
w,b,llv = fitDist(w,b,data,layers1,layers2,iterations;hotvars=Int64[],obsweights=false,α=0.001,β1=0.9,β2=0.999,ϵ=1e-8,c=3.0)
```
### Function evalPDF
```julia
x = evalPDF(obs,layers1,layers2,w,b)
```
### Function evalCDF
```julia
x = evalCDF(obs,layers1,layers2,w,b)
```
### Function limitsCDF
```julia
inf,sup = limitsCDF(layers1,layers2,w,b)
```
### Function quantileCDF
```julia
x = quantileCDF(cvars,p,layers1,layers2,w,b;accuracy=1e-8,boundLow=-1e6,boundUpp=1e6)
```
## Categorical distributions

### Function initCatDist
```julia
w,b,npars = initCatDist(nvars,ncats,layers;shift=0.1)
```
### Function fitCatDist
```julia
w,b,llv = fitCatDist(w,b,data,categories,layers,iterations;hotvars=Int64[],obsweights=false,α=0.001,β1=0.9,β2=0.999,ϵ=1e-8,c=3.0)
```
### Function evalCatPDF
```julia
x = evalCatPDF(obs,categories,layers,w,b)
```
### Function evalCatCDF
```julia
x = evalCatCDF(obs,categories,layers,w,b)
```
### Function quantileCatCDF
```julia
x = quantileCatCDF(cvars,p,categories,layers,w,b)
```
