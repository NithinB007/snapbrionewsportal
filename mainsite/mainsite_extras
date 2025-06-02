from django import template
from django.urls import reverse

register = template.Library()

@register.filter
def absolute_url(value, request):
    """
    Returns the absolute URL of an object based on the request.
    Usage: {{ object.get_absolute_url|absolute_url:request }}
    """
    if not request:
        return value # Fallback if request is not available
    
    # Assuming value is the path returned by get_absolute_url
    return request.build_absolute_uri(value)
