# terraform-provider-demo

    2020 Ondrej Sika <ondrej@ondrejsika.com>
    https://github.com/ondrejsika/terraform-provider-demo


## Example Usage

```terraform
provider "demo" {
  api_origin = "http://127.0.0.1"
  token = "xxx"
}

resource "demo_box" "primary" {
  name = "Primary Box"
}

resource "demo_text" "hello" {
  box_id = demo_box.primary.id
  text = "This is my first box"
}

resource "demo_text" "foo" {
  box_id = demo_box.primary.id
  text = "Foo bar ..."
}

resource "demo_box" "secondary" {
  name = "Secondary Box"
}

resource "demo_text" "secondary" {
  box_id = demo_box.secondary.id
  text = "..."
}
```
