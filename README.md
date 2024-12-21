# Express.js JSON Body Parsing Issue

This repository demonstrates a common issue encountered when working with JSON request bodies in Express.js applications.  The problem arises when the client omits the `Content-Type: application/json` header in their request, leading to the server failing to correctly parse the request body.

## Problem

The provided `bug.js` file contains an Express.js server that attempts to parse JSON request bodies using `express.json()`.  However, if a client sends a POST request without specifying the `Content-Type` header or specifies an incorrect header, the `req.body` will be empty, leading to unexpected behavior and potential errors.

## Solution

The `bugSolution.js` file offers a solution by adding a middleware function to handle cases where the `Content-Type` header is missing or incorrect. This middleware checks for the `Content-Type` and adds it if it's missing or sets it correctly if incorrect.