##Materialize
  Assets/JavaScript/Application.js
    //= require materialize-sprockets

##Create new app:
  rails new <app_name> -d=postgresql -T
            #why postgresql???
      OR

  tiybe <app_name> -T
            #go-to template
            #delete puma duplicate

  Notes:
            # -T removes tests from app

##Create Database
  rake db:create

##Add Migrations
  rails g resource <table_name(sl)> <column>:string
  rails g resource user name:string email:string password:password_digest
  rails g resource <table_name(sl)> master:belongs_to body:text

  rails g migration AddMasterToSlave master:references
  rails g migration AddColumnsToUsers name:string
        admin:boolean

  rails d resource <table_name(sl)> ... ##drops table

  validations:
    , null: false
    , unique: true
    , default: ""    (for boolean)

  #polymorphism:
  http://guides.rubyonrails.org/association_basics.html
    rails g resource tagging tag:belongs_to post:belongs_to
      (no built in generator for has_many or polymorphic associations)

    class CreateTaggings < ActiveRecord::Migration[5.0]
      def change
        create_table :taggings do |t|
          t.string  :name
          t.integer :taggable_id
          t.string  :tagable_type
          t.timestamps
        end

        add_index :pictures, [:imageable_type, :imageable_id]
      end
    end

  #self-joins
    rails g migration AddParentIdToTabs

      def change
        add_column :tabs, :parent_tab_id, :integer
      end

##Seeds
  10.times do
    User.create!(column: "column")
  end

  users.each do |name|
    User.create!(name: name)
  end

  ## it auto-generates id's incrementally.
  ## still need to generate user_id's, post_id's, etc

##Models
  belongs_to :singular
    , :counter_cache: true
  has_many :plurals
    , :dependent => :destroy

  paginates_per 20 #kaminari

  validates :name
    , presence: true
    , length { minimum: 1, maximum: 30 }
    , uniqueness: true


  polymorphism:
    Class Photo
      has_many :taggings, as: :taggable
      has_many :tags, through: :taggings
    end

    Class Tagging
      belongs_to :tag
      belongs_to :photo, polymorphic: true

##Routes
  Check them, before you wreck them

  resources :users

##Controller Actions
  index
  show
  new
  create
  edit
  update
  destroy

##React
  rails g react:component <section>
