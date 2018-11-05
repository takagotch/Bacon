### Bacon
---
.rb
https://github.com/chneukirchen/bacon

```ruby
require 'bacon'
describe 'A new array' do
  before do
    @ary = Array.new
  end
  it 'should be empty' do
    @ary.should.be.empty
    @ary.should.not.include 1
  end
  it 'should have zero size' do
    @ary.size.should.equal 0
    @ary.size.should.be.close 0.1, 0.5
  end
  it 'should raise on trying fetch any index' do
    lambda { @ary.fetch 0 }.
      should.raise(IndexError).
      message.should.match(/out of array/)
    should.raise(IndexError) { @ary.fetch 0 }
  end
  it 'should have an object identity' do
    @ary.should.not.be.same_as Array.new
  end
  palindrome = lambda { |obj| obj == obj.reverse }
  it 'should be a palindrome' do
    @ary.should.be.a palindrome
  end
  it 'should have super powers' do
    should.flunk "no super powers found"
  end
end

shared "an empty container" do
  it "should have size zero" do
  end
  it "should be empty" do
  end
end
context "A new array" do
  behaves_like "an empty container"
end

def shorter_than(max_size)
  lambda { |obj| obj.size < max_size }
end

```

```
bacon whirlwind.rb
bacon -q whirlwind.rb
bacon -p whirlwind.rb
bacon -p whirlwind.rb | taptap -q

bacon -k whirlwind.rb
bacon -k whirlwind.rb | kn-sum

require 'bacon'
(6*9).should.equal 42

```

```
```
