# Expo Camera: accessing cameraRef before mount causes errors

This repository demonstrates a common error encountered when using the Expo Camera API.  The issue arises when attempting to access the `cameraRef` before the component has fully mounted and initialized the camera.  The example showcases the problem and provides a solution using the `useEffect` hook and its dependency array to ensure `cameraRef` is accessed only after it is properly initialized.

## Problem

Accessing the `cameraRef` prematurely leads to errors like `TypeError: Cannot read properties of null (reading 'current')`.  This occurs because `cameraRef.current` is `null` until the camera component mounts and sets the reference.

## Solution

The solution uses a conditional check within the `useEffect` hook to ensure that `cameraRef.current` is not accessed until after the component has mounted and initialized the camera.