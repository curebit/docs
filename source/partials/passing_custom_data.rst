.. raw:: html

  <h2>Passing Custom Person Data</h2>

``person_custom_properties`` is a variable that allows you to pass custom data to Talkable in the form of Key-Value pairs via integration. ``person_custom_properties`` has robust uses as you are able to define and pass any key value pairs you wish. The values you define for some key should be JSON Key-Value pairs themselves, this means complex data structures can be passed through. Any ``person_custom_properties`` data passed through is tied to the Person (Advocate or Friend), that means there is only one instance of each field in existence at any time: the most recently passed data.

All data associated with ``person_custom_properties`` is available for use across all Campaign Views. Accessing this data beings by creating a variable to store your custom_properties:

.. code-block:: javascript

  {% assign data = advocate_info.custom_properties %}

Key Value pairs can be referenced through your newly created object by referencing the value name such as:

.. code-block:: javascript

  {{ data.favorite_color }}

Defining person_custom_properties in your integration might look something like this:

.. code-block:: javascript

  var _curebit_order_details = {
    ...
    person_custom_properties: {
      person_occupation: 'marketing',
      height: '72 inches',
      eye_color: 'brown',
      birthday: '07/03/1983'
    }
    ...
  }
