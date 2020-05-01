<h1 align="center">Struct n' Array JSON 1.1.0</h1>

<p align="center">Replacement for ds_map/ds_list-based JSON encoding/decoding</p>

<p align="center"><a href="https://github.com/JujuAdams/struct-n-array-JSON/releases/tag/1.1.0">Download the .yymps here</a></p>

&nbsp;

-----

&nbsp;

### sna_to_json(struct/array, [pretty], [alphabetizeStructs]) ###

Turns struct and array nested data into a JSON string. The root data type can be either a struct or an array. Setting `[pretty]` to `true` will format the JSON string in a more pleasing human-readable way, whereas setting `[alphabetizeStructs]` to `true` will output the struct variables in ascending alphabetical order. Using pretty and/or alphabetized output does incur a performance penalty.

&nbsp;

### json_to_sna(string) ###

Decodes a JSON string into nested struct/array data. This function will happily ignore formatting whitespace and handles `\\`, `\"`, `\n`, `\r`, and `\t` escaped characters. Also supports `true`, `false`, and `null` values.

&nbsp;

### sna_to_binary(struct/array) ###

Returns a buffer that holds binary encoded struct and array nested data. The root data type can be either a struct or an array. This is substantially faster than `sna_to_json()`.

&nbsp;

### binary_to_sna(buffer, [offset], [size], [destroyBuffer]) ###

Unpacks binary encoded struct/array data. An `[offset]` and total `[size]` for the data within the buffer can be specified which is helpful for working with composite buffers. Set `[size]` to `-1` to use the entire size of the buffer. If `[destroyBuffer]` is set to `true` then the input buffer will be destroyed once the function has finished executing.
