### Formulários do Rails em Modal do Bootstrap
----------------------------------------------

Antes de tudo, instale a `gem bootstrap-sass` em seu projeto, acesse [aqui](https://github.com/twbs/bootstrap-sass).

Crie o arquivo `modal_responder.rb` com o conteúdo abaixo e salve em `app/services`

    class ModalResponder < ActionController::Responder
      cattr_accessor :modal_layout
      self.modal_layout = 'modal'

      def render(*args)
        options = args.extract_options!
        if request.xhr?
          options.merge! layout: modal_layout
        end
        controller.render *args, options
      end

      def default_render(*args)
        render(*args)
      end

      def redirect_to(options)
        if request.xhr?
          head :ok, location: controller.url_for(options)
        else
          controller.redirect_to(options)
        end
      end
    end
---

Insira o método abaixo em seu `application_controller.rb`

    def respond_modal_with(*args, &blk)
      options = args.extract_options!
      options[:responder] = ModalResponder
      respond_with *args, options, &blk
    end
---

Insira a `div` abaixo em seu `application.html.erb`

    <div id="#modal-holder">
    </div>
---

Crie o arquivo `modal.html.slim` em `views/layouts`

    #mainModal.modal.custom.fade aria-hidden="true" aria-labelledby="mainModalLabel" role="dialog" tabindex="-1" 
      .modal-dialog
        .modal-content
          .modal-header
            button.close data-dismiss="modal" type="button" 
              span aria-hidden="true"  ×
              span.sr-only Fechar
            h4#mainModalLabel.modal-title
              = yield :title if content_for? :title
          = yield
---

Crie o arquivo `modal.js.coffe` com o conteúdo abaixo e salve em `app/assets/javascripts`

    $ ->
      modal_holder_selector = '#modal-holder'
      modal_selector = '.modal'

      $(document).on 'click', 'a[data-modal]', ->
        location = $(this).attr('href')
        #Load modal dialog from server
        $.get location, (data)->
          $(modal_holder_selector).html(data).
          find(modal_selector).modal()
        false

      $(document).on 'ajax:success',
        'form[data-modal]', (event, data, status, xhr)->
          url = xhr.getResponseHeader('Location')
          if url
            # Redirect to url
            window.location = url
          else
            # Remove old modal backdrop
            $('.modal-backdrop').remove()

            # Replace old modal with new one
            $(modal_holder_selector).html(data).
            find(modal_selector).modal()

          false
---

Não se esqueça de incluir o código em seu `application.js`

    //= require modal
---

No seu `controller` de preferência, insira as seguintes linhas e métodos

    respond_to :html, :json
    before_action :modal_responder, only: [:show, :edit]

    ...

    def new
      respond_modal_with @object = Class.new
    end

    ...

    private

      ...

      set_object
        @object = Class.find(params[:id])
      end

      def modal_responder
        respond_modal_with set_object
      end
---

Em suas `views`, altere os seus links para habilitar o `modal`

    tr
      td
        = link_to 'Show', object, data: { modal: true }
      td
        = link_to 'Edit', edit_object_path(object), data: { modal: true }
    ...


    = link_to 'New Object', new_object_path, data: { modal: true }
---

No arquivo `new.html.slim` e `edit.html.slim` use o seguinte código

    = content_for :title, 'Título do modal'

    == render 'form'
---

No arquivo `form.html.slim` altere a estrutura do formulário para que o mesmo se encaixe na estrutura do `modal`

    = form_for @object do |f|

      .modal-body

        = f.label :label
        = f.text_field :field

      .modal-footer

        = f.button 'Enviar'
---

Com isso você já pode usar o `modal` em seus formulários e outras páginas.

Referência: [5 Steps to Add Remote Modals to Your Rails App](http://www.jetthoughts.com/blog/tech/2014/08/27/5-steps-to-add-remote-modals-to-your-rails-app.html)
