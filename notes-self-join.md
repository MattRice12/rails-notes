## Migrations
  rails g migration AddParentIdToTabs

  def change
    add_column :tabs, :parent_tab_id, :integer
  end

## Models
Tab Model
  has_many   :children, -> { order :id }, class_name: "Tab", foreign_key: :parent_tab_id

  belongs_to :parent, class_name: "Tab", foreign_key: :parent_tab_id, optional: true

  # If you want to find the top-most tab
      def tab_root
        tab = self
        while tab.parent
          tab = tab.parent
        end
        tab
      end

## Views
  #Call the Children:
    tab.children.each do |child|
      child.name
    end

  #Call the parent:
    tab.parent.name

  #Call the siblings:
    tab.parent.children.each do |sibling|
      sibling.name
    end

  #Call the root
    tab.tab_root.name

## Other (Maybe exceptions to all of these)
  1) There is always going to be at least 1 tab without a parent_tab_id
  2) Children can have only 1 parent :(
  3) Parents can have many children :(
