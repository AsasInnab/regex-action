
# regex-action
This action matches a string against a regex pattern and outputs the first match

## Inputs

### `regex_pattern`

**Required** The regex pattern to test with (e.g. "**JIR-[0-9]+**")

### `regex_flags`

The regex flags (e.g. "**gim**")

### `search_string`

**Required** The string to test against (e.g. "**My jira ticket number is JIR-12345**")

## Outputs

### `first_match`

First regex match (e.g. "JIR-12345")

## Example usage

	- name: Find JIRA ticket references
	  id: jira
      uses: AsasInnab/regex-action@v1
      with:
	    regex_pattern: 'JIR-[0-9]+'
	    regex_flags: 'gim'
	    search_string: ' My jira ticket number is JIR-12345'
	- name: Echo JIRA reference
      run: echo "My JIRA ticket number is ${{ steps.jira.outputs.first_match }}"
